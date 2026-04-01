# 附录E · 数据流架构图

核心数据流
```typescript
用户输入 →  命令解析 →  查询引擎 →  ClaudeAPI  →  工具执行 →  UI渲染 →  用户 ↓  ↓  ↓  ↓  ↓  ↓  权限检查 技能匹配
Token 预算 流式处理 结果缓存 差异更新 ↓  ↓  ↓  ↓  ↓  ↓  Hook链 工具池 缓存断点 错误恢复 记忆提取 帧优化
KAIROS自主Agent数据流
<tick> 心跳 →  模型推理 →  工具决策 →  执行 →  结果评估 ↓  ↓  Sleep工具 ← ─ ─ ─ ─ ─ ─  无有用工作 ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─  判断
──→ 继续 ↓  ↓  Channel通知 ← ─ ─  外部消息 ─ ─ →  唤醒 ─ ─ →  响应 ─ ─ →  发送 ↓  PushNotification  →  用户设备
记忆系统数据流
会话对话 →  Session  Memory提取（10Ktoken 触发）→ 临时文件 ↓  多个会话 →  AutoDream（24h+5 会话触发）→
Memory 目录 ↓  文件读取 →  Magic  Docs检测 →  Sonnet  Agent更新 →  项目文件 ↓  Memory目录 →  Team  Sync  →
秘密扫描 →  云端API → 团队成员
Bridge远程控制数据流
外部系统（桌面/Web/CI ） ↓  Work请求 →  Bridge  Loop  →  Spawn会话 →  Claude  CLI实例 ↓  ↓  JWT认证 →  REPL
Bridge ← WebSocket → 消息转发 ↓  ↓  权限请求 →  用户端UI ← 转发 →  远程权限桥接
```