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

## 安装方法

推荐使用 `npx skills add` 命令安装：

```bash
# 从 GitHub 仓库安装
npx skills add github:Astrid-code/agent-skills read-arxiv-paper

# 或从本地安装
npx skills add ./skills/read-arxiv-paper
```

安装后即可在 Claude Code 中使用 `/read-arxiv-paper` 命令。

## 许可证

MIT License