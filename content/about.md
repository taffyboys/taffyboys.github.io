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

## 风格定位

当前博客采用暖色极简风格，视觉上参考了 Anthropic 网站的克制感，但没有复制其品牌素材或官方字体。

整体设计目标是：

- **淡色背景**：使用接近纸张的奶油白，让页面更柔和。
- **大留白**：减少视觉噪音，让注意力回到文字本身。
- **低饱和强调色**：链接、标签和交互状态使用淡陶土色，避免过重。
- **清晰阅读层级**：标题、摘要、正文、代码块和表格各自保持明确边界。
- **轻量交互**：卡片 hover、导航状态和按钮反馈都尽量克制。

让文章安静、稳定、好读。

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

其中 `-D` 表示预览草稿文章。

### 添加已有的 markdown 文章

如果你已经有写好的 `.md` 文件，直接把它复制到 `content/posts/` 目录，然后在文件最顶部加上 frontmatter 即可：

```toml
+++
title = '文章标题'
date = 2026-07-09
description = '简短摘要'
tags = ['标签1']
categories = ['分类名']
draft = false
+++

（这里是你原来的 markdown 正文...）
```

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

## 图片引用

把图片放到 `static/images/` 目录（如果目录不存在，自己创建即可），然后在 markdown 中用**绝对路径**引用：

```markdown
![图片描述](/images/example.png)
```

## 构建与发布

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

推送后可以在Github Actions 查看构建进度。

## 维护与扩展

这个博客的维护原则是：

> 内容优先，样式克制；结构简单，长期可维护。

后续如果继续扩展，可以优先考虑：

- 添加 About 页面中的个人介绍
- 添加 favicon
- 添加文章目录
- 添加站内搜索
- 添加深色模式
- 优化移动端细节

## 常用命令速查

| 命令 | 用途 |
|------|------|
| `hugo new posts/文件名.md` | 创建新文章骨架 |
| `hugo server -D` | 本地预览（含草稿） |
| `hugo` | 本地构建（输出到 `public/`） |
| `git add -A && git commit -m "说明" && git push` | 推送所有改动 |
