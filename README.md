# AI Tips

一个独立的 Hugo 博客仓库，用来记录我的每日 AI 学习与实战。

## 技术栈

- Hugo Extended `>= 0.127.0`
- Theme: [`ddnio/hugo-ashe`](https://github.com/ddnio/hugo-ashe)

## 本地运行

```bash
git submodule update --init --recursive
hugo server
```

本地访问：[http://localhost:1313/](http://localhost:1313/)

## 新增一篇笔记

```bash
hugo new content posts/day-xx-topic.md
```

建议 front matter 保持这几个字段：

- `title`
- `date`
- `categories`
- `tags`
- `summary`

## 部署

仓库内置 GitHub Pages 工作流：`.github/workflows/pages.yml`。
推送到 `main` 分支后会自动构建并发布。
