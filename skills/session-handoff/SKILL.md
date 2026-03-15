---
name: session-handoff
description: Generate a handoff document when context limits approach, enabling seamless continuation by another AI agent session
version: "1.0.0"
---

When the current session is about to end (e.g., approaching context limits), generate a handoff document at `./{YYMMDD}-handoff.md` for the next AI agent to continue the work.

## Output Structure

### 任务概览 (Task Overview)
State what needs to be accomplished, expected deliverables, and the definition of done.

### 已完成工作 (Work Completed)
List all analyses, confirmations, modifications, investigations, discussions, or outputs already done.

### 核心背景 (Core Context)
Include:
- Key background information
- User's explicit requirements
- Known constraints and limitations
- Critical decisions already made
- Important assumptions

### 重要发现 (Key Findings)
Highlight the most significant conclusions, patterns, anomalies, root causes, design decisions, or noteworthy information discovered.

### 待办事项 (Remaining Work)
List items still requiring attention, sorted by priority.

### 后续行动建议 (Recommended Actions)
Guide the next agent on:
- Which files, modules, data, logs, commands, or pages to inspect first
- What to validate before proceeding
- Recommended immediate next steps

### 风险提示 (Risks & Warnings)
Note potential pitfalls, common mistakes, directions already explored and ruled out.

## Guidelines

- This document targets the next AI agent, not the user
- Be specific and actionable; avoid vague statements
- Reference concrete names: file paths, class names, module names, API endpoints, commands, terminology
- Prioritize information that enables immediate continuation
- End with "快速启动建议" (Quick Start Advice) for immediate first action