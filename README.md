# agent-skills

Claude Code Skills 集合，提供可复用的技能模块。

## 可用 Skills

### read-arxiv-paper

阅读和分析 arXiv 论文，生成通俗易懂的中文总结。

**使用方法：**
```
/read-arxiv-paper https://arxiv.org/abs/xxxx.xxxxx
```

**功能：**
- 自动下载论文 LaTeX 源码
- 提取论文标题
- 生成结构化中文笔记：背景、核心问题、方法、结论、启发

**输出：**
- 缓存：`~/.cache/arxiv-papers/{arxiv_id}/`
- 笔记：`./papers/{title}/notes.md`

### session-handoff

在上下文即将耗尽时生成交接文档，使后续 AI 会话能无缝继续工作。

**使用方法：**
```
/session-handoff
```

**使用场景：**
- 当前会话接近上下文限制
- 需要切换到新会话继续复杂任务
- 跨会话的长期项目

**输出：**
- 文件：`./{YYMMDD}-handoff.md`
- 包含：任务概览、已完成工作、核心背景、重要发现、待办事项、后续行动建议、风险提示

## 安装方法

推荐使用 `npx skills add` 命令安装：

```bash
# 从 GitHub 仓库安装
npx skills add github:Astrid-code/agent-skills read-arxiv-paper
npx skills add github:Astrid-code/agent-skills session-handoff

# 或从本地安装
npx skills add ./skills/read-arxiv-paper
npx skills add ./skills/session-handoff
```

安装后即可在 Claude Code 中使用 `/read-arxiv-paper` 和 `/session-handoff` 命令。

## 许可证

MIT License