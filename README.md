# MediaWiki-Assistant

一个基于 Dify 工作流的 MediaWiki 助手，用于将用户输入的 Markdown 转换为符合 MediaWiki 规范的页面内容，并支持自动写入指定的 Wiki 实例。

## 功能概览

- 支持两种入口：
  - `add`：将 Markdown 转换为 MediaWiki 格式，生成标题、摘要，并自动写入 Wiki。
  - `chat`：基于知识库检索结果回答问题。
- 使用外部转换服务将 Markdown 转换为 MediaWiki 源码。
- 通过 LLM 生成标题、概览与编辑摘要。
- 使用 Wiki API 进行登录与页面写入。

## 工作流结构（简要）

- **用户输入** → **条件分支**（`add` / `chat`）
- `add` 分支：Markdown 转换 → LLM 整理 → 变量拆解 → Wiki 写入
- `chat` 分支：知识检索 → LLM 基于检索回答

## 依赖

- Marketplace 插件：`langgenius/moonshot`、`langgenius/tongyi`

## 说明

该项目的核心配置位于 `MediaWiki-Assistant.yml`，可直接导入 Dify 进行使用和二次调整。