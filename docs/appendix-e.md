# 附录E · 数据流架构图

核心数据流
用户输入 →  命令解析 →  查询引擎 →  C l a u d e  A P I  →  工具执行 →  U I渲染 →  用户 ↓  ↓  ↓  ↓  ↓  ↓  权限检查 技能匹配
Token 预算 流式处理 结果缓存 差异更新 ↓  ↓  ↓  ↓  ↓  ↓  H o o k链 工具池 缓存断点 错误恢复 记忆提取 帧优化
KAIROS自主Agent数据流
< tick > 心跳 →  模型推理 →  工具决策 →  执行 →  结果评估 ↓  ↓  S l e e p工具 ← ─ ─ ─ ─ ─ ─  无有用工作 ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─  判断
──→ 继续 ↓  ↓  C h a n n e l通知 ← ─ ─  外部消息 ─ ─ →  唤醒 ─ ─ →  响应 ─ ─ →  发送 ↓  P u s h N o t i f i c a t i o n  →  用户设备
记忆系统数据流
会话对话 →  S e s s i o n  M e m o r y提取（10K token 触发）→ 临时文件 ↓  多个会话 →  A u t o D r e a m（24h+5 会话触发）→
Memory 目录 ↓  文件读取 →  M a g i c  D o c s检测 →  S o n n e t  A g e n t更新 →  项目文件 ↓  M e m o r y目录 →  T e a m  S y n c  →
秘密扫描 →  云端API → 团队成员
Bridge远程控制数据流
外部系统（桌面/Web/CI ） ↓  W o r k请求 →  B r i d g e  L o o p  →  S p a w n会话 →  C l a u d e  C L I实例 ↓  ↓  J W T认证 →  R E P L
Bridge ← WebSocket → 消息转发 ↓  ↓  权限请求 →  用户端UI ← 转发 →  远程权限桥接