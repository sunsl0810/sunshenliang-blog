# 孙思良的博客

基于 [Hugo](https://gohugo.io/) + [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 的静态博客，部署在 Cloudflare Pages。

## 本地预览

```bash
hugo server -D
```

打开 http://localhost:1313 。改文件会热更新，`-D` 表示同时渲染草稿。

> 需要 Hugo **v0.169.0 extended** 或更高版本。装法见 https://gohugo.io/installation/

## 写新文章

```bash
hugo new content posts/文章-slug.md
```

然后编辑 `content/posts/文章-slug.md`，把 `draft: true` 改成 `false`。

## 手动构建

```bash
hugo --gc --minify
```

产物在 `public/`。

## Cloudflare Pages 部署参数

| 配置项 | 值 |
|---|---|
| Framework preset | Hugo |
| Build command | `hugo --gc --minify` |
| Build output directory | `public` |
| 环境变量 `HUGO_VERSION` | `0.169.0` |

⚠️ 主题是**直接放在 `themes/PaperMod/` 目录里的**（不是 git submodule）。推仓库时务必确保这个目录一起提交，否则云端构建会找不到主题。

## 目录说明

```
content/posts/   文章（Markdown）
content/about.md 关于页
hugo.toml        全站配置：标题、菜单、社交链接
static/          原样拷贝到站点根目录的文件（favicon、图片等）
themes/PaperMod/ 主题
```
