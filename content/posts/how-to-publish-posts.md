+++
title = '如何发布新文章'
date = 2026-07-08T22:48:00+08:00
description = '一篇简短的指南，介绍如何用 Hugo 创建新文章并推送到 GitHub Pages。'
tags = ['hugo', 'git', 'github-pages']
categories = ['tech']
draft = false
+++

## 创建新文章

使用 Hugo 的内置命令即可快速生成文章骨架：

```bash
hugo new posts/我的新文章.md
```

执行后会在 `content/posts/` 目录下生成一个带有 frontmatter 的 markdown 文件：

```toml
+++
title = '我的新文章'
date = 2026-07-08
description = ''
tags = []
categories = []
draft = true
+++
```

你只需要：

1. 填写 `description`（文章摘要，会显示在列表里）
2. 添加 `tags` 和 `categories`
3. 把 `draft` 改为 `false`
4. 在 `+++` 下方写正文

## Frontmatter 字段说明

| 字段 | 说明 | 示例 |
|------|------|------|
| `title` | 文章标题 | `如何发布新文章` |
| `date` | 发布日期（自动生成） | `2026-07-08` |
| `description` | 摘要，显示在文章列表中 | `一篇简短的指南...` |
| `tags` | 标签数组，自动生成标签页 | `['hugo', 'git']` |
| `categories` | 分类数组，自动生成分类页 | `['tech']` |
| `draft` | 草稿状态，`true` 时不会部署到线上 | `false` |

## 本地预览

写文章时可以在本地启动预览服务器，实时查看效果：

```bash
hugo server -D
```

`-D` 参数会显示草稿文章（`draft: true` 的也会显示）。打开浏览器访问 `http://localhost:1313/` 即可预览。

保存 markdown 文件后，页面会自动刷新。

## 推送到 GitHub Pages

文章写好后，通过 Git 推送到 GitHub，Actions 会自动构建和部署：

```bash
# 1. 查看改动
git status

# 2. 添加新文章
git add content/posts/我的新文章.md

# 3. 提交
git commit -m "新增文章: 如何发布新文章"

# 4. 推送（触发自动部署）
git push
```

推送后可以在 `https://github.com/taffyboys/taffyboys.github.io/actions` 查看构建进度。构建完成后，新文章就会出现在 `https://taffyboys.github.io/` 上。

## 常用命令速查

| 命令 | 用途 |
|------|------|
| `hugo new posts/文件名.md` | 创建新文章骨架 |
| `hugo server -D` | 本地预览（含草稿） |
| `hugo` | 本地构建（输出到 `public/`） |
| `git add -A && git commit -m "说明" && git push` | 推送所有改动 |

就是这么简单——写 markdown，`git push`，剩下的交给 Hugo 和 GitHub Actions。
