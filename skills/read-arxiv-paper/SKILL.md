---
name: read-arxiv-paper
description: Use this skill when asked to read an arxiv paper given an arxiv URL
version: "1.0.0"
---

You will be given a URL of an arxiv paper, for example:

https://www.arxiv.org/abs/2601.07372

### Part 1: Normalize the URL

The goal is to fetch the TeX Source of the paper (not the PDF!), the URL always looks like this:

https://www.arxiv.org/src/2601.07372

Notice the /src/ in the url. Once you have the URL:

### Part 2: Download the paper source

Fetch the url to a local .tar.gz file. A good location is `~/.cache/arxiv-papers/{arxiv_id}.tar.gz`.

(If the file already exists, there is no need to re-download it).

### Part 3: Unpack the file

Unpack the contents into `~/.cache/arxiv-papers/{arxiv_id}` directory.

### Part 4: Get Paper Title

Fetch the arxiv abstract page (e.g., https://arxiv.org/abs/2601.07372) and extract the paper title from the page.

Then sanitize the title to create a safe directory name:
- Convert to lowercase
- Replace spaces with underscores
- Remove or replace special characters (keep only alphanumeric, underscores, and hyphens)

Create the output directory: `./papers/{sanitized_title}/`

### Part 5: Locate the entrypoint

Every latex source usually has an entrypoint, such as `main.tex` or something like that.

### Part 6: Read the paper

Once you've found the entrypoint, Read the contents and then recurse through all other relevant source files to read the paper.

### Part 7: Report

Once you've read the paper, produce a summary of the paper into a markdown file at `./papers/{sanitized_title}/notes.md`.

The summary should be written for a general audience (非专业学者), using clear and accessible language:

1. **背景 (Background)**: 这篇论文要解决什么问题？为什么这个问题重要？
2. **核心问题 (Core Problem)**: 论文关注的核心问题是什么？
3. **方法 (Approach)**: 作者提出了什么方法来解决这个问题？用通俗易懂的语言解释关键思路。
4. **结论 (Conclusions)**: 主要发现和结论是什么？
5. **启发 (Insights)**: 这项工作有什么启发意义？可能的扩展方向？

Writing guidelines:
- Avoid excessive technical jargon; when necessary, provide clear explanations
- Use analogies and examples to explain complex concepts
- Focus on the "why" and "how" rather than technical implementation details
- Make it engaging and readable for someone without deep expertise in the field