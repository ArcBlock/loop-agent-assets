# arc/deploy-log — nightly build log（可信事实层，ArcBlock/arc#1698）

老冒（#1698）的诉求：nightly build 光「能跑」不够，必须让人**一眼确认今天线上是哪一次
build、是好是坏**，而且「区分 build 失败 vs 前天的旧版本」——现在两者都表现为「看不见」。
这里就是那份**可查的事实源**：每次部署由 `ArcBlock/arc` 的 deploy skill 写入一条脚本生成的
结构化 record（不是 AI 叙述——老冒点名 nightly build log「过去都是脚本写的」）。

生成引擎：`ArcBlock/arc` 的 `scripts/deploy-changelog.ts`（+ `.test.ts`）。
写入者：`ArcBlock/arc` 的 `.claude/skills/deploy/SKILL.md`（GitHub MCP 文件写）。

## 路径约定

```
arc/deploy-log/<env>/<YYYY-MM-DD>.json   ← 当次 record（同日多次可加 -HHMMSS 后缀）
arc/deploy-log/<env>/latest.json         ← 始终指向最新一次 record（页脚 build-info 读这个）
arc/deploy-log/<env>/<YYYY-MM-DD>.md     ← 当次人类可读报告（按 commit 归组；Slack 链接指向它）
arc/deploy-log/<env>/latest.md           ← 始终指向最新一次报告
arc/deploy-log/<env>/index.md            ← 每次追加一行（时间 / commit / 状态 / run），反向可查
```

- `<env>` = `test` | `staging`。
- **JSON 是机读事实源、Markdown 是人读报告**，两者同源（deploy skill 从同一份 record 派生：
  `--format record` → JSON，`--format report` → Markdown）。
- **`latest.json` 是「失败 vs 陈旧」判据的关键**：它的 `status` + `finishedAt` 让任何人（和
  test 页脚 build-info）一眼知道最近一次 build 成功没、是什么时候。失败时 `latest.json.status
  = "failure"`，而线上 serving 的仍是上一次成功版本——两者对比即可区分「今天 build 失败了」
  与「这只是前天的旧版本」。

## Record schema（`schema: 1`）

| 字段 | 类型 | 说明 |
|---|---|---|
| `schema` | number | schema 版本（当前 `1`） |
| `env` | `"test"｜"staging"` | 部署目标环境 |
| `status` | `"success"｜"failure"｜"cancelled"` | CI run 的 conclusion |
| `startedAt` | ISO-8601 UTC? | 触发时刻（best-effort） |
| `finishedAt` | ISO-8601 UTC | record 产出时刻（部署完成） |
| `commit` | string | build/deploy 的完整 commit SHA |
| `commitShort` | string | 前 9 位短 SHA |
| `runUrl` | string? | GitHub Actions run URL（回溯 raw log） |
| `range` | `{since?,base?}` | 改动窗口的计算方式 |
| `blocklets` | `BlockletChange[]` | 各 blocklet 更新日志；**无改动的 blocklet 不出现** |

`BlockletChange = { name, commits: { sha, shortSha, subject }[] }`。

### 例子（`arc/deploy-log/test/latest.json`，节选）

```json
{
  "schema": 1,
  "env": "test",
  "status": "success",
  "startedAt": "2026-07-18T18:00:01Z",
  "finishedAt": "2026-07-18T18:12:34Z",
  "commit": "1efe67d334cd2fb210bb5e94491d18728b6d6d82",
  "commitShort": "1efe67d33",
  "runUrl": "https://github.com/ArcBlock/arc/actions/runs/123456",
  "range": { "since": "24 hours ago" },
  "blocklets": [
    {
      "name": "site-arcblock-io",
      "commits": [
        { "sha": "6a22d796a...", "shortSha": "6a22d796a", "subject": "feat(blocklets): ..." }
      ]
    }
  ]
}
```

## 人类可读报告（`<date>.md` / `latest.md`）

`--format report` 生成，**按 commit 归组**：一个 monorepo commit 常一次改动几十个 blocklet，
报告把「同一改动」的 blocklet 归到那个 commit 下**只列一次**（`影响 N 个 blocklet（同一改动）：
a、b、c`），而不是逐 blocklet 重复整条 commit（#1248，yechao 07-18）。commit 按影响的 blocklet
数从多到少排序，最值得合并的浮到最上面。

## 消费方

- **Slack 精简通知**：deploy skill 从同一 record 派生 `--format slack` 文案（status + 改动规模
  计数 + `<date>.md` 报告链接，**不逐 blocklet 展开**），发 engineering channel。细节在报告里。
- **页脚 build-info（test 环境，#1698 下一个 slice）**：读 `arc/deploy-log/test/latest.json` 的
  `finishedAt` / `commitShort` / `status`，在 test 页面页脚展示 build 时间 / 版本 / 状态。
- **人**：直接读 `index.md` 一眼看历史，或 `latest.json` 看当前线上状态。
