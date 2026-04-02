# Claude Code 0331 系统报告

> 基于 2026.03.31 npm Source Map 泄露版本的深度技术分析

---

**1,884 files · 394,222 lines · 54 tools · 89 feature flags**  
**30 chapters · 6 appendices · 12 parts**

来源：公众号「手工川」| 2026.04.01
补充研究：Xiao Tan（[@tvytlx](https://x.com/tvytlx)）| 公众号「Xiao Tan AI」
整理：[Nicole](https://nicoles.garden/) | X：[@chenyuq56901969](https://x.com/chenyuq56901969)

---

## 核心发现速览

| 维度 | 数据 |
|------|------|
| 源文件总数 | 1,884 个 .ts/.tsx |
| 总代码行数 | 394,222 行 |
| 工具数量 | 54 个（含门控工具） |
| 特性标志 | 89 个 |
| 命令目录 | 117 个 |
| Source Map 大小 | 59.8 MB |

---

## 事件背景

2026年3月31日，区块链公司 Solayer 的实习生 Chaofan Shou 在对 Anthropic 发布于 npm 的 Claude Code 安装包进行常规检查时，发现包中包含了一个 `cli.js.map` 文件（59.8MB）。

这不是黑客攻击——这是一个 **CI/CD 流程配置失误**，导致 Claude Code 全部 TypeScript 源码（包含开发者手写注释）以明文形式嵌入在 Source Map 中公开发布。

---

## 架构总览

```
KETER（主协调器 main.tsx）
├── CHOKHMAH（查询引擎 QueryEngine）
├── CHESED（54个工具生态）
├── GEVURAH（七层安全防护）
├── TIFERET（KAIROS 自主Agent核心）
├── NETZACH（插件与技能生态）
├── HOD（Bridge 远程控制）
├── YESOD（四层记忆架构）
├── BINAH（上下文与环境感知）
└── MALKUTH（终端UI框架）
```

---

## 目录导航

点击左侧边栏，可以按章节阅读完整报告。

| 部分 | 核心内容 |
|------|---------|
| [第1-2章](docs/ch01) | 事件始末 & 全景统计 |
| [第3-6章](docs/ch03) | 启动系统、查询引擎、Token经济学 |
| [第7-10章](docs/ch07) | 54个工具、BashTool安全、权限模型 |
| [第11-13章](docs/ch11) | **KAIROS自主Agent**（核心亮点） |
| [第14章](docs/ch14) | 四层记忆架构 |
| [第15-16章](docs/ch15) | Bridge远程控制系统 |
| [第17-18章](docs/ch17) | 自定义Ink框架（19,842行） |
| [第19-21章](docs/ch19) | 插件生态 & 技能系统 & MCP |
| [第22-23章](docs/ch22) | 七层安全防护 & 企业功能 |
| [第24-26章](docs/ch24) | 隐藏命令 & Buddy宠物 & Computer Use |
| [第27-28章](docs/ch27) | 设计模式 & 性能工程 |
| [第29-30章](docs/ch29) | 产品路线图推演 & 竞争格局 |

---

*本报告仅用于学术研究和技术讨论，不涉及任何代码的再分发或商业利用。*
