## ✅ Deploy test · `811e51a48` · success

- **时间**: 2026-08-05T17:22:15Z
- **版本**: `811e51a485bc7083e8ad733122ad9e3db881bac7`
- **改动窗口**: 24 hours ago

**12 个 blocklet 有改动**

### 改动摘要

- 12 个 blocklet 同受一次共享依赖改动影响：arc、chain-explorer、did-space、showcase、todo、observability-explorer、aistro、arch-qa、discuss-kit、blocklet-manager、mailbox-demo、settings-cascade — discoverRuns 查询改走 trace 索引，不再全表扫描（Phase 4）（[#3107](https://github.com/ArcBlock/arc/issues/3107)）
- **observability-explorer**：/traces 页隐藏了用不上的检查器面板，同时修复了一处会导致 UI 构建直接失败的语法问题（[#3176](https://github.com/ArcBlock/arc/issues/3176)、[#3130](https://github.com/ArcBlock/arc/issues/3130)）
- **showcase**：首页 Explore 导航新增 Docs 入口（[#3164](https://github.com/ArcBlock/arc/issues/3164)）；networkRead 声明补上了自证机制（[#3142](https://github.com/ArcBlock/arc/issues/3142)）
- **discuss-kit**：关闭 SessionUserAFS 的 base-fallthrough 读通道，破坏性变更（[#3117](https://github.com/ArcBlock/arc/issues/3117)）

---
Run: https://github.com/ArcBlock/arc/actions/runs/31029017768
