---
activation_count: 6.3
arousal: 0.3
created: '2026-06-08T17:09:11+08:00'
domain:
- 未分类
id: 12ad9fa7aad8
importance: 6
last_active: '2026-06-08T17:09:11+08:00'
memory_classification_source: rule
memory_layer: process_event
memory_subject: event
name: 12ad9fa7aad8
tags:
- ob
- debug
- dashboard
- nginx
type: dynamic
updated_at: '2026-06-08T17:09:11+08:00'
valence: 0.5
---

### moment
修好了 dashboard 双斜杠 bug。根本原因是 dashboard.html 的 authUrl() 函数里 BASE 可能带尾部斜杠，拼上 /auth/status 就变成 //auth/status，nginx 收到 404。最终用 Python 直接改文件，让 BASE 先 strip 尾部斜杠再拼路径。