# test-sweep QA Report — aside（PR #1334 v2，内联截图）

> 🤖 AI Agent @ vm · runner:Claude · skills@90f0261 — 响应 li-yechao 07-12 15:46 反馈的三点，重跑 `/test-sweep --app aside`。本文件为**内联截图版**（GitHub 直接渲染图片，非链接）。对应 issue #1391 / PR #1334。

## 关键修正（对上一版 #1391 的纠正）
- **骨架屏不是 #1220 P0 bug，是我上一版 wait 太短（5s）的误判。** 改为**等数据加载稳定**（最长 30s、越过中间平台）后，feed / collections / tags **真实数据全部加载出来**（feed 2 条 item，见下图），全 21 路由 `skeletonRemain=0`。**我撤回上一版"复现 #1220"的错误结论**，向你致歉。
- **加载耗时已记录**（每路由 `数据加载ms` 列）——数据到齐耗时 6–20s，是报告的一部分。
- **深入数据+操作**：新增"点进第一条真实 item → 详情弹窗（含 Edit/Delete/Collections/Tags 操作）"的走查（drill，4 条），见交互表。

---

<!-- test-sweep-blocklet: aside -->
## ✅ aside

**URL**: https://aside.afsd.dev
**测试时间**: 2026-07-12T16:03:22Z

### 后端探针

| 探针 | 结果 |
|---|---|
| http-reachable | ✅ HTTP 200 |
| afs-rpc-list | ✅ ok:true (11 .aup pages) |
| afs-rpc-authed-list-/user | ✅ ok:true (Bearer 可读) |

### UI 走查

| 路由 | 认证 | 结果 | 数据加载ms | 总耗时ms | 截图 | 详情 |
|---|---|---|---|---|---|---|
| / | anon | ✅ | 6085 | 7345 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-root.png) | — |
| /app | anon | ✅ | 9406 | 10931 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app.png) | — |
| /app | authed | ✅ | 19965 | 31718 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-authed.png) | Failed to load resource: the server responded with a status of 404 () ×8 |
| /app/collections | anon | ✅ | 7542 | 11967 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections.png) | — |
| /app/collections | authed | ✅ | 19831 | 29356 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections-authed.png) | Failed to load resource: the server responded with a status of 404 () ×2 |
| /app/collection-detail 🔗动态 | anon | ✅ | 10368 | 11884 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collection-detail.png) | — |
| /app/collection-detail 🔗动态 | authed | ✅ | 18938 | 25615 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collection-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×4 |
| /app/item-detail 🔗动态 | anon | ✅ | 7260 | 8909 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-item-detail.png) | — |
| /app/item-detail 🔗动态 | authed | ✅ | 18782 | 25617 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-item-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×4 |
| /app/tags | anon | ✅ | 7354 | 8843 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tags.png) | — |
| /app/tags | authed | ✅ | 8933 | 15852 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tags-authed.png) | Failed to load resource: the server responded with a status of 404 () |
| /app/publish | anon | ✅ | 7927 | 9064 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-publish.png) | — |
| /app/explore | anon | ✅ | 7677 | 9297 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-explore.png) | — |
| /app/tag-detail 🔗动态 | anon | ✅ | 7540 | 9181 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tag-detail.png) | — |
| /app/tag-detail 🔗动态 | authed | ✅ | 19693 | 26219 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tag-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×4 |
| /app/clipper | anon | ✅ | 7469 | 9054 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-clipper.png) | — |
| /app/clipper | authed | ✅ | 7872 | 14712 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-clipper-authed.png) | — |
| /app/clip | anon | ✅ | 7462 | 8954 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-clip.png) | — |
| /app/clip | authed | ✅ | 7523 | 10601 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-clip-authed.png) | — |
| /app/settings | anon | ✅ | 11045 | 12982 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-settings.png) | — |
| /app/settings | authed | ✅ | 8429 | 16469 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-settings-authed.png) | — |

### 交互走查（authed，安全无写）

| 路由 | 交互 | 结果 | 截图 | 说明 |
|---|---|---|---|---|
| /app | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-authed-drill.png) | 点进列表项 → 详情已打开（/app?item=A3679615-5723-4286-80CE-22BDB63034CB&presentation=card）✓ |
| /app | open:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-authed-int-1.png) | overlay opened ✓ |
| /app/collections | open:Language/empty-validate | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections-authed-int-1-emptyvalidate.png) | empty submit blocked by validation (no write) ✓ |
| /app/collections | open:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections-authed-int-1.png) | overlay opened ✓ |
| /app/collections | open:New Collection/empty-validate | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections-authed-int-2-emptyvalidate.png) | empty submit blocked by validation (no write) ✓ |
| /app/collections | open:New Collection | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collections-authed-int-2.png) | overlay opened ✓ |
| /app/collection-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-collection-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/collection-detail?item=A3679615-5723-4286-80CE-22BDB63034CB&presentation=card）✓ |
| /app/item-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-item-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/item-detail?item=A3679615-5723-4286-80CE-22BDB63034CB&presentation=card）✓ |
| /app/tags | open:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tags-authed-int-1.png) | overlay opened ✓ |
| /app/tag-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-tag-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/tag-detail?item=A3679615-5723-4286-80CE-22BDB63034CB&presentation=card）✓ |
| /app/clipper | open:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-clipper-authed-int-1.png) | overlay opened ✓ |
| /app/settings | open:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v2-20260712T160952Z/aside.aside.afsd.dev-app-settings-authed-int-1.png) | overlay opened ✓ |

**汇总**: ✅ 路由 pass=21 fail=0 skip(动态需:id)=0 · 交互走查 12 项

