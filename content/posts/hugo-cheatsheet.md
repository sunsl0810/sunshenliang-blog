---
title: "Hugo 写作速查表"
date: 2026-11-05T21:30:00+08:00
draft: false
tags: ["Hugo", "速查"]
categories: ["技术"]
summary: "常用 front matter、短代码和目录结构的备忘，忘的时候翻一眼。"
---

写久了总会忘，索性整理成一份速查表。

## 新建文章

```bash
hugo new content posts/slug.md
```

文件会落在 `content/posts/slug.md`，并按 `archetypes/default.md` 生成头部。

## Front matter

```yaml
---
title: "文章标题"
date: 2026-11-05T21:30:00+08:00
draft: false
tags: ["Hugo", "速查"]
categories: ["技术"]
summary: "列表页显示的摘要"
---
```

`draft: true` 的文章不会被打包，但 `hugo server -D` 时可见。

## 本地预览

```bash
hugo server -D
```

默认在 `http://localhost:1313`，改文件会热更新。

## 几个常用短代码

折叠块：

{{</* collapse title="点开看看" */>}}
里面可以放任意 Markdown。
{{</* /collapse */>}}

图片带说明：

{{</* figure src="/images/demo.png" caption="图注" */>}}

## 目录结构

```
sunshenliang-blog/
├── content/
│   ├── posts/          # 文章
│   ├── about.md
│   └── search.md
├── themes/PaperMod/    # 主题
├── hugo.toml           # 全站配置
└── static/             # 原样拷贝的文件
```

`static/` 下的东西会原封不动出现在站点根目录，放 favicon、图片、`CNAME` 之类最方便。
