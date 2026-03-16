# Claude Code 新手模板

让 Claude Code 更懂你的项目。一套开箱即用的 CLAUDE.md 模板和实用 Skills。

## 使用方法

### 第一步：下载模板

在你的项目中打开 Claude Code，输入：

```
帮我从 https://github.com/lighthouse-strategy/claude-code-starter 下载 CLAUDE.md 到项目根目录，skills 文件夹下载到 .claude/skills/
```

### 第二步：配置项目信息

```
/setup
```

Claude 会逐步问你项目的基本信息，自动填写模板中的占位符。

## 模板包含什么

### CLAUDE.md — 项目规则文件

| 区块 | 作用 |
|------|------|
| 回复语言与风格 | 让 Claude 用中文回复，保持简洁 |
| 项目基本信息 | 告诉 Claude 你的项目是什么 |
| 代码规范 | 统一命名、commit 格式、分支策略 |
| 安全铁律 | 防止泄露密钥、误删文件等危险操作 |
| 工作流程 | 确保先读代码再改、改完先测试再提交 |
| 不要做什么 | 明确禁止 Claude 的行为，避免帮倒忙 |
| 已知陷阱 | 记录项目的坑，Claude 不会再踩 |

### Skills — 实用技能

| 命令 | 作用 |
|------|------|
| `/setup` | 交互式配置项目信息 |
| `/commit` | 安全提交：lint 检查 + 敏感信息扫描 + 规范 commit message |
| `/review` | 代码审查：安全性、可读性、潜在 bug 三维度检查 |
| `/debug` | 系统化调试：禁止猜测，逐步定位根因 |

## 进阶用法

### 全局 CLAUDE.md

除了项目级的 CLAUDE.md，你还可以创建一个全局配置，让所有项目共享通用规则（比如「用中文回复」）：

```
帮我把这个 repo 的 global-CLAUDE.md 的内容保存到 ~/.claude/CLAUDE.md
```

### 已经有项目了？

如果你的项目已经有代码，也可以先让 Claude 自动生成一个基础版：

```
/init
```

然后再参考本模板补充你需要的规则。
