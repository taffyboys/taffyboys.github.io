+++
title = 'Hello World'
date = 2026-07-08
description = '欢迎来到我的 Hugo 博客！这是一篇示例文章，展示 markdown 的各种排版效果。'
tags = ['hugo', 'markdown']
categories = ['tech']
draft = false
+++

欢迎来到我的博客！这是用 Hugo 搭建的第一篇文章。下面展示一些常见的 Markdown 排版效果。

## 标题与段落

这是一段普通的文字。Hugo 会把 markdown 渲染成干净的 HTML，你只需要专注于写作本身。

## 列表

无序列表：

- 第一项
- 第二项
  - 嵌套项 A
  - 嵌套项 B
- 第三项

有序列表：

1. 步骤一
2. 步骤二
3. 步骤三

## 代码块

Hugo 内置 Chroma 语法高亮，支持各种语言：

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Hugo!")
}
```

行内代码则用反引号包裹，比如 `hugo server -D`。

## 引用

> 好的博客，是写给未来的自己的信。
> —— 某位博主

## 表格

| 功能 | 是否支持 | 说明 |
|------|---------|------|
| 标签 | 是 | 通过 frontmatter 的 tags 字段 |
| 分类 | 是 | 通过 frontmatter 的 categories 字段 |
| 语法高亮 | 是 | Chroma 内置，零依赖 |

## 链接与图片

这是一个 [Hugo 官网](https://gohugo.io) 的链接。

## 开始写作

要创建新文章，只需运行：

```
hugo new posts/my-second-post.md
```

然后编辑生成的 markdown 文件，写好后把 `draft` 改为 `false` 即可发布。享受写作吧！
