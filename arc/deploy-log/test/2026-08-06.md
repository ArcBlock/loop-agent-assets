## ❌ Deploy test · `dbc1cc036` · failure

- **时间**: 2026-08-06T17:38:44Z
- **版本**: `dbc1cc0367f38daad3b917bea049184dd9697e65`
- **改动窗口**: 24 hours ago

**失败原因**：本次部署未能实际执行任何构建/部署步骤。CI run
（[#31122404116](https://github.com/ArcBlock/arc/actions/runs/31122404116)）的
`deploy` job 在 `queued` 状态卡了约 15 分钟（17:23:41 → 17:38:43）后被 GitHub 判定为
`cancelled`（从未分配到 runner，无任何 step 日志）。触发到 job 真正开始排队之间也有约
12 分钟的 workflow 级 `pending`。同一时间段内，仓库其他 workflow（`Deploy Staging`、
`Issue Chain`）也同时卡在 `queued`/`pending`，且整个仓库连续 20+ 分钟 0 个 run 处于
`in_progress` —— 判断为 GitHub Actions runner 队列在账号/组织层面出现积压，不是本次
代码改动或 `deploy-test.yml` 配置的问题。

**12 个 blocklet 有改动**（本窗口内，未实际部署）

### 改动摘要

- **showcase**：修复了指向失效 demo 数据的 network-read 绑定，改指回真实挂载点（`3d18f1e91` / #3222）
- **observability-explorer**：修复 showcase-dsl 编译测试用的过期 fixture，改指到 `data/items`（`dfa85fd12` / #3268）
- **arch-qa**：部署脚本按环境派生 `MIGRATE_HOST`，去掉已失效的 arcblock.io staging 路由（`1139d7bfd`）
- 其余 9 个 blocklet（arc、chain-explorer、did-space、todo、aistro、discuss-kit、blocklet-manager、mailbox-demo、settings-cascade）本窗口内仅带了 release chore 提交（`3c3857d8a`），无用户可见改动。

_以上改动均未实际部署到 test 环境——本次 CI run 因 runner 队列积压被取消，线上仍在跑上一次成功 build（见 `latest.json`）。_
