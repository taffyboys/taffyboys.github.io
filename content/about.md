+++
title = '博客说明'
date = 2026-07-09
description = '关于这个博客的定位、结构、写作方式与维护说明。'
tags = ['blog', 'hugo']
categories = ['notes']
draft = false
+++

## 这是什么

这是一个基于 [Hugo](https://gohugo.io/) 搭建的个人博客，用来记录技术笔记、学习过程、生活观察和一些阶段性的想法。

博客的名字是 **Mocong's Blogs**。它更像是一间安静的小书房：不追求复杂功能，也不试图承载太多信息，只希望把值得留下的内容写得清楚、放得整洁。

## 风格定位

当前博客采用暖色极简风格，视觉上参考了 Anthropic 网站的克制感，但没有复制其品牌素材或官方字体。

整体设计目标是：

- **淡色背景**：使用接近纸张的奶油白，让页面更柔和。
- **大留白**：减少视觉噪音，让注意力回到文字本身。
- **低饱和强调色**：链接、标签和交互状态使用淡陶土色，避免过重。
- **清晰阅读层级**：标题、摘要、正文、代码块和表格各自保持明确边界。
- **轻量交互**：卡片 hover、导航状态和按钮反馈都尽量克制。

这个博客的重点不是“炫技”，而是让文章安静、稳定、好读。

## 内容组织

主要内容放在：

```text
content/posts/
```

每篇文章都是一个 Markdown 文件。文章通过 front matter 描述标题、日期、摘要、标签和分类。

示例：

```toml
+++
title = '文章标题'
date = 2026-07-09
description = '这是一段文章摘要。'
tags = ['hugo', 'notes']
categories = ['tech']
draft = false
+++
```

常用字段说明：

| 字段 | 用途 |
|------|------|
| `title` | 文章标题 |
| `date` | 发布时间 |
| `description` | 文章摘要，会显示在列表和文章页标题区 |
| `tags` | 标签，用于主题聚合 |
| `categories` | 分类，用于内容归档 |
| `draft` | 是否为草稿，`false` 才会正式发布 |

## 如何写新文章

可以使用 Hugo 命令创建新文章：

```bash
hugo new posts/my-new-post.md
```

也可以手动在 `content/posts/` 下创建 Markdown 文件。

写作流程建议：

1. 创建文章文件。
2. 填写 front matter。
3. 在正文中使用 Markdown 写作。
4. 本地预览。
5. 确认无误后发布。

本地预览命令：

```bash
hugo server -D
```

然后打开：

```text
http://localhost:1313/
```

其中 `-D` 表示预览草稿文章。

## 项目结构

当前项目的主要目录如下：

```text
.
├── assets/
│   └── css/
│       └── main.css          # 博客主样式
├── content/
│   ├── about.md              # 当前说明页
│   └── posts/                # 博客文章
├── layouts/
│   ├── _default/             # 通用页面模板
│   ├── partials/             # 页头、页脚、文章卡片等组件
│   └── index.html            # 首页模板
├── static/                   # 静态资源，如图片、favicon 等
└── hugo.toml                 # Hugo 配置文件
```

几个关键文件：

| 文件 | 作用 |
|------|------|
| `hugo.toml` | 站点标题、描述、分类法和 Markdown 渲染配置 |
| `assets/css/main.css` | 全站视觉样式 |
| `layouts/index.html` | 首页结构 |
| `layouts/_default/single.html` | 单篇文章和独立页面模板 |
| `layouts/partials/header.html` | 顶部导航 |
| `layouts/partials/footer.html` | 底部文案 |
| `layouts/partials/article-card.html` | 文章列表卡片 |

## 当前页面特性

这个博客目前包含：

- 首页 Hero 区域
- 最近文章列表
- 文章详情页
- 标签页
- 分类页
- 阅读时间显示
- 代码高亮
- 关闭代码块行号
- 简洁 Markdown 表格样式
- 404 页面
- RSS 输出

## 写作建议

为了让博客保持简洁利落，建议文章也保持统一的写法：

- 标题尽量具体，不要太泛。
- 每篇文章写一段 `description`，方便列表页阅读。
- 标签不宜过多，通常 2 到 5 个即可。
- 代码块注明语言，例如 `bash`、`go`、`toml`。
- 表格只在确实能提升理解时使用。
- 图片尽量压缩后放入 `static/images/`。

图片引用示例：

```markdown
![图片说明](/images/example.png)
```

## 构建与发布

生成静态站点：

```bash
hugo --minify
```

构建后的文件会输出到：

```text
public/
```

如果部署到 GitHub Pages，通常只需要把仓库推送到 GitHub，并通过 GitHub Actions 或 Pages 配置完成发布。

## 维护原则

这个博客的维护原则是：

> 内容优先，样式克制；结构简单，长期可维护。

后续如果继续扩展，可以优先考虑：

- 添加 About 页面中的个人介绍
- 添加 favicon
- 添加文章目录
- 添加站内搜索
- 添加深色模式
- 优化移动端细节

但这些都不是必须的。对于一个个人博客来说，最重要的仍然是持续写作。

## 最后

愿这里成为一处缓慢积累的地方。

不用急着完整，也不用急着漂亮。  
只要一篇一篇写下去，博客自然会长出自己的形状。
