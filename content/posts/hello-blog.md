---
title: "这个博客是怎么搭起来的"
date: 2026-11-08T10:00:00+08:00
draft: false
tags: ["建站", "Hugo", "Cloudflare"]
categories: ["技术"]
summary: "记一下从腾讯云域名到 Cloudflare Pages 上线的完整过程，方便以后自己回看。"
---

博客上线了。这篇文章记录一下搭建过程，省得以后自己忘了。

## 整体结构

整套东西只有三块：

1. **域名** —— 在腾讯云注册的 `sunshenliang.top`
2. **DNS 与托管** —— Cloudflare 接管解析，并提供静态站点托管
3. **站点本身** —— Hugo 生成的纯静态站点

没有服务器，没有数据库，也没有月费。

## 为什么用静态站点

博客的本质是「把一堆 Markdown 渲染成网页」。这件事在构建时做一次就够了，没有必要每次访问都让服务器现算。

静态站点带来的好处很直接：

- 打开速度快，页面就是 HTML + CSS
- 没有后台，也就没有后台漏洞
- 备份就是备份一个 git 仓库
- 托管免费

代价是评论、搜索这类功能需要额外的第三方服务，不过对个人博客来说够用了。

## 写作流程

新增一篇文章只需要一个命令：

```bash
hugo new content posts/my-new-post.md
```

然后编辑 `content/posts/my-new-post.md`，推送仓库，Cloudflare 自动重新构建。

## 代码高亮

顺便测一下代码块样式：

```python
def fib(n: int) -> int:
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a


print([fib(i) for i in range(10)])
```

## 接下来

- 补上关于页
- 把评论接上（大概会用 Giscus）
- 慢慢写，别为了更新而更新
