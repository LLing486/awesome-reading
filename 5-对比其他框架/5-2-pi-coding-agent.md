# pi — 极简终端编程 Agent

## 项目概览

**pi** 是 Mario Zechner（[@badlogic](https://github.com/badlogic)）开发的**极简终端 AI 编程 CLI**，属于 [pi-mono](https://github.com/badlogic/pi-mono) monorepo 的核心包，npm 包名为 `@mariozechner/pi-coding-agent`。

> *Pi is a minimal terminal coding harness. Adapt pi to your workflows, not the other way around.*

## 核心定位

与 Claude Code、GitHub Copilot 等重型编程 agent 不同，pi 刻意不做 sub-agent、plan mode 等复杂功能，而是**提供扩展性框架**，让用户按需添加。

## 主要功能

### 交互模式
- 类 GPT-style TUI，底部编辑器 + 消息/工具调用分层显示
- 支持 `@` 引用文件、Tab 路径补全、Ctrl+V 贴图、bash `!` 前缀直接执行
- 消息队列：Enter 排队 steering 消息，Alt+Enter 排队 follow-up 消息

### 内置工具
默认只给模型 4 个工具：`read`、`bash`、`edit`、`write`，保持最小化。

### Session 管理
- JSONL 文件存储，内置**树状分支**结构
- `/tree` 可视化导航，任意历史节点继续
- `/fork` 从历史点创建新分支，`/clone` 复制当前分支
- 自动上下文压缩（`/compact`），防止上下文溢出

### 多模型支持
内置支持大量 Provider：

| 类别 | Provider |
|------|----------|
| 主流 | Anthropic Claude Pro/Max、OpenAI ChatGPT Plus/Pro (Codex) |
| 开源友好 | DeepSeek、Google Gemini、GitHub Copilot |
| 国内 | **小米 MiMo**、MiniMax、Kimi For Coding |
| 其他 | Mistral、Groq、Cerebras、Cloudflare Workers AI、xAI、OpenRouter 等 |

### 扩展机制

| 类型 | 说明 |
|------|------|
| **Skills** | 可共享的技能模块 |
| **Prompt Templates** | 提示词模板 |
| **Extensions** | TypeScript 插件 |
| **Themes** | 主题 |
| **Pi Packages** | 通过 npm/git 分发的扩展包 |

### 特色功能

- **`/share`**：一键上传 session 为私有 GitHub Gist，带可分享 HTML 预览
- **Session 分享到 Hugging Face**：鼓励开源项目作者分享编程 session 到 [badlogicgames/pi-mono](https://huggingface.co/datasets/badlogicgames/pi-mono)，用于改进模型训练
- 跨平台：Windows、Termux/Android、tmux 均有官方文档

## 安装使用

```bash
npm install -g @mariozechner/pi-coding-agent

# API Key 方式
export ANTHROPIC_API_KEY=***
pi

# 或 OAuth 登录
pi
/login  # 选择 Provider
```

## 与 Hermes Agent 的对比

| 维度 | pi | Hermes Agent |
|------|----|----|
| **交互形态** | 纯 CLI TUI | 多平台（飞书/Telegram/CLI） |
| **工具集** | 最小化 4 工具，可扩展 | 47 内置工具 + Skills |
| **Session 管理** | 树状分支 JSONL | 会话持久化 + 上下文管理 |
| **扩展方式** | Skills/Extensions/Themes/Packages | Skills + MCP |
| **多模型** | 大量 Provider 内置 | 多种 LLM Provider |
| **多平台** | 专注终端 | 多消息平台 Gateway |
| **设计哲学** | 极简 + 用户扩展 | 能力丰富 + 平台集成 |

**核心区别**：pi 是"给你一个极简框架，自己搭想要的 agent"；Hermes 是"内置强大能力，多平台开箱即用"。

## 相关链接

- GitHub: [badlogic/pi-mono](https://github.com/badlogic/pi-mono)
- npm: [@mariozechner/pi-coding-agent](https://www.npmjs.com/package/@mariozechner/pi-coding-agent)
- Discord: [pi community](https://discord.com/invite/3cU7Bz4UPx)
- Session 数据集: [badlogicgames/pi-mono (Hugging Face)](https://huggingface.co/datasets/badlogicgames/pi-mono)
