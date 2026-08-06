## ⚠️ Deploy staging · `dbc1cc036` · cancelled

- **时间**: 2026-08-06T17:31:43Z
- **版本**: `dbc1cc0367f38daad3b917bea049184dd9697e65`
- **改动窗口**: 24 hours ago
- **Run**: https://github.com/ArcBlock/arc/actions/runs/31122611689

**12 个 blocklet 有改动**

**根因**：这次部署未失败在代码或部署脚本上——job 从触发（17:15:46 UTC）到被取消
（17:30:50 UTC）全程停在 `queued`，`deploy` job 没有分配到 runner（`runner_id: 0`）。
GitHub 当时正在经历一次影响 Actions 的平台级故障（[githubstatus.com](https://www.githubstatus.com/)
报告 Actions "Major Outage"，critical incident 从 ~16:33 UTC 开始，17:02 UTC 的更新写明
"Workflow runs are still failing or delayed in starting, and some queued jobs may time
out"）。本次 job 正是被这个平台超时机制取消的，`scripts/deploy-staging-worker.sh` 从未
被执行，没有产生任何部署日志。**线上 staging 环境未受影响，仍在跑上一次成功部署的版本。**

### 改动摘要

- **showcase**：修复了失效的 network-read demo 绑定，改指向真实 mount（`3d18f1e91` / #3222）
- **observability-explorer**：修复 showcase-dsl 编译测试 fixture 的过期引用，改指向 `data/items`（`dfa85fd12` / #3268）
- **arch-qa**：部署脚本按 env 派生 `MIGRATE_HOST`，去掉失效的 arcblock.io staging 路由（`1139d7bfd`）

其余 9 个 blocklet（`arc`、`chain-explorer`、`did-space`、`todo`、`aistro`、`discuss-kit`、
`blocklet-manager`、`mailbox-demo`、`settings-cascade`）在窗口内只被一次 monorepo 版本号
发布 commit（`chore(main): release 2.0.0-beta.24`）触达，无用户可见改动，从摘要中略去。
