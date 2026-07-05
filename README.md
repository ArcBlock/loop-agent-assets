# loop-agent-assets — 公司统一图床 / 资产仓

给 AI agent（test-sweep / ui-verify / cloud routine 等）和人使用的**公共**资产托管仓：
截图、录屏等需要内嵌进 GitHub issue / PR markdown 的文件都提交到这里，用
`raw.githubusercontent.com` URL 引用。

## 为什么需要这个仓（而不是 release assets / 源仓分支）

- claude cloud routine 沙箱无 `gh`，且 agent proxy 按 session type 硬禁 GitHub release 写
  与网页上传端点（ArcBlock/arc#949 多轮实测）；routine 里唯一已验证可用的写通道是 MCP 文件提交。
- 本仓必须保持 **Public**：私有仓的 raw URL 无法被 GitHub camo 匿名渲染，内嵌即破图。
- 独立仓不受源仓 PR / 分支生命周期影响（分支图床曾因被误合并全坏，见 ArcBlock/arc#907）。

## 路径规则（必须遵守，保证可反向溯源）

```
<source-owner>/<source-repo>/<context>/<UTC时间戳>-<文件名>
<同路径>.md    ← sidecar：source 链接、上传时间、上传者
```

- `<context>`：`issue-<N>`（资产属于某 issue）/ `pr-<N>`（属于某 PR）/
  其它场景用短 slug（如 `test-sweep-20260705`）
- 示例：
  - `ArcBlock/arc/issue-949/20260705-031500-screenshot.png`
  - `ArcBlock/arc/issue-949/20260705-031500-screenshot.png.md`
- 引用 URL：`https://raw.githubusercontent.com/ArcBlock/loop-agent-assets/main/<path>`

## 怎么上传

- 有 `gh` 的环境：用源仓的 `scripts/gh-upload-image.sh`（ArcBlock/arc，自动落 sidecar）
- cloud routine（无 `gh`）：MCP `create_or_update_file` 直接提交，遵守同一路径规则并附 sidecar
  （前提：本仓已加入 routine session 的 repo scope，`add_repo`）

## 纪律

- **只增不改**：文件名带 UTC 时间戳，永不覆盖已有资产——历史 issue / PR 里的内嵌 URL 必须永远有效
- **绝不提交 secret / token / 含敏感信息的截图**
- 本仓只是存储，不参与任何源仓的 PR / CI 流程
