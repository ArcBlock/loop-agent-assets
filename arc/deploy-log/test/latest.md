## ✅ Deploy test · `396ba6cf4` · success

- **时间**: 2026-07-27T08:57:42Z
- **版本**: `396ba6cf4e1848623ae4bda5519aae2479f28ae3`
- **改动窗口**: 24 hours ago

**12 个 blocklet 有改动**

### 改动摘要

- 12 个 blocklet（arc、chain-explorer、did-space、showcase、todo、observability-explorer、aistro、arch-qa、discuss-kit、blocklet-manager、mailbox-demo、settings-cascade）同受一次共享依赖改动影响：aos 的索引搜索结果批量补水（batch-hydrate）+ 修复 `/packages` 与 `/instance` 根路径路由（`478fcd9f2`，#2509）。

> 本次触发说明：`deploy-test.yml` 在 2026-07-25、2026-07-26 连续两天因 `@aigne/blocklet-manager/dist/index.mjs` 模块解析失败（`ERR_MODULE_NOT_FOUND`，已在关闭的 #2425/#2426/#2464 追踪）而失败，修复已于 #2505 合并（2026-07-27T05:53:02Z），但部署 workflow 在 #2095 之后已改为仅 `workflow_dispatch` 手动触发（无每日 cron），未再自动重新部署——本次是 issue-sweep 在核实 #2484（discuss-kit test-sweep 失败）时发现 live 环境仍在跑修复前的旧 build（`/app` 客户端 bundle 404，全站卡在 "CONNECTING"），因而手动触发的一次追平部署。部署已成功，`main`（含 #2505、#2510、#2513）已发布到 test 环境。
