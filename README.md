# yishanby 的博客

网站：**https://yishanby.github.io**

基于 GitHub Pages、Jekyll 和 Minima。提交到 `main` 后，GitHub 自动生成并发布网站。包含中文页面、手机适配、文章归档、RSS、站点地图和代码高亮。

## 直接在 GitHub 上写文章

1. 打开本仓库，点击 **Add file → Create new file**。
2. 输入文件路径，例如 `_posts/2026-10-26-my-first-post.md`。将日期替换成实际发布日期；英文短标题用于文章网址，以后尽量保持不变。
3. 粘贴下面的模板，填写标题和正文。
4. 点击 **Commit changes**，提交到 `main`。
5. 等待仓库 **Actions** 中的 `pages build and deployment` 成功，刷新博客。通常需要几分钟。

```markdown
---
title: "我的第一篇文章"
tags: [随笔]
---

这里写摘要，会出现在首页文章列表中。

<!-- more -->

## 开始

这里写正文。
```

也可以从 [`_drafts/first-post.md`](_drafts/first-post.md) 复制模板。`_drafts` 目录里的内容不会发布到网站；本仓库是公开的，所以仓库中的草稿仍然可以被别人查看。私密草稿建议只保存在本地。

如果一天有多篇文章，请用不同的英文短标题。文件名中的未来日期不会提前发布，也不会自动在该日期触发构建；到时需要再提交一次。

## 添加图片

在仓库中使用 **Add file → Upload files** 上传到 `assets/images/`，然后在文章中插入：

```markdown
![图片说明](/assets/images/example.png)
```

## 常用修改

| 要修改什么 | 编辑文件 |
| --- | --- |
| 博客名称、简介、作者 | `_config.yml` |
| 首页介绍文字 | `_layouts/home.html` |
| 关于我 | `about.md` |
| 颜色和排版 | `assets/main.scss` |
| 编辑或删除文章 | `_posts/` 中的对应文件 |

## 本地预览（可选）

仅在希望本地写作时需要安装 Ruby 和 Bundler；直接在 GitHub 网页写作无需安装。

```sh
bundle install
bundle exec jekyll serve --livereload
```

打开 http://127.0.0.1:4000 。若要预览草稿，使用 `bundle exec jekyll serve --drafts`。修改 `_config.yml` 后需重新启动预览服务。

## 发布设置

仓库 **Settings → Pages**：

- Source：**Deploy from a branch**
- Branch：**main**
- Folder：**/ (root)**
- Enforce HTTPS：启用

构建失败时，在 **Actions** 中打开失败的任务查看原因。文章开头的 YAML 配置必须由两行 `---` 包围；包含冒号等字符的标题请使用引号。

## 以后绑定自己的域名

购买域名后，在 **Settings → Pages → Custom domain** 设置域名，按照 [GitHub 官方文档](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) 配置 DNS，并将 `_config.yml` 中的 `url` 改为新地址。域名配置完成后确认 HTTPS 已开启。

Minima 主题使用 MIT 许可，见 `LICENSE-theme.txt`。文章内容的权利归作者所有。
