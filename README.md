# loop-agent-assets — 公司统一图床 / 资产仓

给 AI agent（test-sweep / ui-verify / cloud routine 等）和人使用的**公共**资产托管仓：
截图、录屏等需要内嵌进 GitHub issue / PR markdown 的文件提交到这里，用
`raw.githubusercontent.com` URL 引用。

## 为什么需要这个仓（而不是 release assets / 源仓分支）

- claude cloud routine 沙箱无 `gh`，且 agent proxy 按 session type 硬禁 GitHub release 写
  与网页上传端点（ArcBlock/arc#949 多轮实测）；routine 里唯一已验证可用的写通道是 MCP 文件提交。
- 本仓必须保持 **Public**：私有仓的 raw URL 无法被 GitHub camo 匿名渲染，内嵌即破图。
- 独立仓不受源仓 PR / 分支生命周期影响（分支图床曾因被误合并全坏，见 ArcBlock/arc#907）。

## 路径规则（与 ArcBlock/arc#1039 合入的 skill 约定一致）

```
{repo-slug}/{context}/...            ← 顶层按源 repo 短名分目录（如 arc/）
```

- **ui-verify（PR 截图/录屏）**：`arc/pr{N}/{TS}-{文件名}`，索引 `arc/pr{N}/index.md`（追加行，反向可查）
- **test-sweep（巡检截图）**：`arc/ts-{TS}/{文件名}`，索引 `arc/ts-{TS}/index.md`（一次性写入）
- 其它场景：`{repo-slug}/{issue-N | 短slug}/{TS}-{文件名}`，同目录放 `index.md` 或同名 `.md` 回链
- 引用 URL：`https://raw.githubusercontent.com/ArcBlock/loop-agent-assets/main/<path>`

每个目录必须有 `index.md`（或每资产一个同名 `.md`）写明来源 issue / PR / run——
这是「从图床反向找到出处」的硬要求。

## 怎么上传

- 有 `gh` 的环境：`ArcBlock/arc` 的 `scripts/gh-upload-image.sh`（无 `gh` 时 exit 2）
- cloud routine（无 `gh`）：MCP `create_or_update_file` 直接提交（见 arc 仓 test-sweep /
  ui-verify SKILL 的 Path B；前提：本仓已加入 routine session 的 repo scope，`add_repo`）

## 纪律

- **只增不改**：文件名 / 目录带 UTC 时间戳或 PR 号，永不覆盖已有资产——历史 issue / PR
  里的内嵌 URL 必须永远有效
- **绝不提交 secret / token / 含敏感信息的截图**
- 本仓只是存储，不参与任何源仓的 PR / CI 流程
