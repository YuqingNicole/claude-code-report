# Claude Code 源码深度研究报告（第二篇）

> 作者：Xiao Tan | X: [@tvytlx](https://x.com/tvytlx) | 公众号：Xiao Tan AI
>
> 基于 `@anthropic-ai/claude-code` npm 包的 `cli.js.map` 还原源码后完成的系统性研究

---

本报告与手工川版报告**互为补充**：

| 维度 | 手工川版 | 本报告（Xiao Tan 版）|
|------|---------|---------------------|
| 侧重点 | 系统架构全景 | Prompt 机制 + Agent 调度链 |
| 章节数 | 30章 + 6附录 | 10章 |
| 特色 | 广度优先，覆盖所有子系统 | 精度优先，深挖核心机制 |

---

## 章节导航

| 章节 | 主题 |
|------|------|
| [第1章](docs/report2/r2-ch01) | 研究范围与结论总览 |
| [第2章](docs/report2/r2-ch02) | 源码结构全景 |
| [第3章](docs/report2/r2-ch03) | 系统提示词总装 |
| [第4章](docs/report2/r2-ch04) | Prompt 全量提取与模块级拆解 |
| [第5章](docs/report2/r2-ch05) | Agent Prompt 与 built-in agents |
| [第6章](docs/report2/r2-ch06) | Agent 调度链深挖 |
| [第7章](docs/report2/r2-ch07) | Skills / Plugins / Hooks / MCP |
| [第8章](docs/report2/r2-ch08) | 权限、Hook、工具执行链 |
| [第9章](docs/report2/r2-ch09) | 为什么 Claude Code 这么强 |
| [第10章](docs/report2/r2-ch10) | 关键文件索引 |
