# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Claude Code Skills 集合仓库，提供可复用的技能模块。

## Project Structure

```
agent-skills/
├── skills/               # Skills 目录
│   └── read-arxiv-paper/ # arXiv 论文阅读 skill
│       └── SKILL.md
├── README.md             # 项目说明
└── CLAUDE.md             # Claude Code 指引
```

## Adding New Skills

新增 skill 时：
1. 在 `skills/` 下创建新目录
2. 添加 `SKILL.md` 文件，包含 frontmatter (name, description) 和具体步骤
3. 更新 README.md 说明用法