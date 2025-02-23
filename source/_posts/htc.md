---
title: 如何参与
date: 2025-02-24 00:00:01
sticky: 2147483647
coauthor:
  - team
categories:
  - 指南
tags:
  - 指南
mathjax: true
---

协作流程与博文撰写指南。

<!-- more -->

![简易协作流程图](workflow.svg)

## 准备工作

在开始之前，您需要

1. 注册一个 [GitHub 账户](https://docs.github.com/zh/get-started/start-your-journey/creating-an-account-on-github)。
2. 联系管理员加入 [LZUPAT GitHub 组织](https://github.com/LZUPAT)。

如果您还需要在本地编辑，则需要安装

1. [Git](https://git-scm.com/) 或 [GitHub Desktop](https://docs.github.com/zh/desktop/overview/about-github-desktop)：用于与 GitHub 交互。

   其中 Git 功能强大但入门难度较高，GitHub Desktop 大幅简化了 Git 相关操作，如果您不熟悉 Git 的相关操作，那么推荐从 GitHub Desktop 开始。

2. [Yarn](https://yarnpkg.com)：用于安装博客框架等。
3. [Pandoc](https://pandoc.org)：用于博客的渲染。[^1]

[^1]: 注意**添加环境变量**。

参与本站的撰写不需要高超的 Git/Node.js/... 技巧，只需要按照下面的步骤操作就好啦！

## 具体流程

[GitHub 官方文档](https://docs.github.com/zh/get-started/exploring-projects-on-github/contributing-to-a-project) 中有简要介绍。

一次完整的贡献流程如下：

1. 如果您没有创建过本仓库的副本，则您首先需要**创建本仓库的副本**（fork）。
2. 之后在您的副本上**进行修改**。
3. 最后向主仓库**创建拉取请求**（open a pull request），等待管理员处理。
4. 当您的修改并入主仓库后，您可以删除您的副本。如果您选择保留副本，则在下次参与修改之前您可能需要**手动同步**主仓库（Sync fork）。

### 创建仓库副本

首先打开仓库地址 <https://github.com/LZUPAT/blog>，点击右侧的 "Fork" 按钮：

![](fork-1.png)

之后会进入类似下图的页面：

![](fork-2.png)

其中 "Repository name" 不能和您账户中已有的仓库重名。接下来点击 "Create fork"，点击后会自动跳转到 fork 好的仓库页面：

![](fork-3.png)

其中

- <font color=#00A2E8>蓝色</font>方框的部分为分支（branch）的相关信息。
- <font color=#A349A4>紫色</font>方框的部分可以获取该仓库的下载链接等信息。
- <font color=#FF7F27>橙色</font>方框的部分用于和主仓库互动。点击 "Contribute" 下拉菜单可以向主仓库创建拉取请求；点击 "Sync fork" 下拉菜单则会将当前分支和主分支同步。

这些部分我们会在后面进一步介绍。

### 在仓库副本中进行修改

首先，无论您是在网页上操作还是在本地操作，都推荐您**新建一个分支**，并在新分支上操作，**保持主分支不变**。因为主分支的主要任务是和主仓库同步，而如果副本的主分支上有您的修改，则在同步时会更加复杂，有时甚至难以完成。

创建和删除分支的步骤可以在 [GitHub 的官方文档](https://docs.github.com/zh/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) 中找到，这里简要叙述一下创建分支的步骤。

首先点击带有分支图标 <i class="fa fa-code-branch"></i> 的下拉菜单：

![](new-branch-1.png)

点击 "View all branches"，跳转到分支管理页面：

![](new-branch-2.png)

点击 "New branch"，在文本框中输入新分支名：

![](new-branch-3.png)

点击 "Create new branch"，这样新分支就建好了：

![](new-branch-4.png)

点击蓝色的新分支名即可切换到新分支：

![](new-branch-5.png)

注意到带有分支图标的下拉菜单文本变为了新分支名字，这就说明我们成功切换了分支。

接下来我们就可以正式开始修改了：

{% tabs modify %}

<!-- tab 在线修改 -->

如果需要修改现存文件，可以点击对应文件：

{% asset_img "edit-online-1.png" %}

点击 <i class="fa fa-pen"></i> 图标，跳转到在线编辑器：

{% asset_img "edit-online-2.png" %}

在您完成修改后，点击 "Commit changes..." 提交：

{% asset_img "edit-online-3.png" %}

撰写合适的 Commit message 后点击 "Commit changes" 就完成提交了。

如果需要上传新文件，则首先点击目标文件夹，接下来点击 "Add file" 下拉菜单，按照您的需求继续选择即可，和修改现存文件的流程基本一致。

{% note warning %}
**注意**：完成提交后会可能会切换当前分支，若您还需要继续修改请特别留意。
{% endnote %}

<!-- endtab -->

<!-- tab 本地修改 -->

本地修改的操作较为复杂，若您不熟悉 Git，建议使用在线修改。

具体流程可参见 [Git - OI Wiki](https://oi-wiki.org/tools/git/)。

<!-- endtab -->

{% endtabs %}

### 创建拉取请求

另请参阅：[GitHub 官方文档](https://docs.github.com/zh/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)。

在您完成修改后，通常 GitHub 会提示您创建拉取请求：

![](open-pull-request-1.png)

如果没有该提示，则可以切换到存储了您修改的分支后点击 "Contribute" 下拉菜单后点击 "Open pull request"：

![](open-pull-request-2.png)

之后会跳转到如下界面：

![](open-pull-request-3.png)

注意：

1. 请保持下方的 "Allow edits by maintainers" 为勾选状态，否则可能会影响管理员的工作。
2. 标题长度不宜过长。为方便管理，标题需要按固定格式撰写。标题格式为 `<修改类型>(<文件名/分类>): <修改的内容>`，其中 `<修改类型>` 为以下之一：

   - `feat`：用于添加内容的情况。
   - `fix`：用于修正现有内容错误的情况。
   - `refactor`：用于对一个页面进行较大规模的更改的情况。
   - `revert`：用于回退之前更改的情况。
   - `style`：用于修改文本或代码的格式的情况。
   - `ci`：用于修改维护脚本、自动化配置的情况。
   - `chore`：用于维护依赖等的情况。

   以下是一些例子：

   - `feat(htc.md): 具体流程的叙述`
   - `fix(about.md): typo`
   - `ci(pages.yml): 优化部署流程`
   - `chore(deps): bump hexo from 7.2.0 to 7.3.0`

向下滚动可以看到您修改的详细信息，核实无误后点击 "Create pull request" 就完成了。

## 博文的撰写方法

- 博文使用 Markdown 撰写，Markdown 语法可参见 [Markdown Cheat Sheet | Markdown Guide](https://www.markdownguide.org/cheat-sheet/)。

  如有必要，您也可以在博文中书写 HTML 以获得更加自由的样式控制（如用 `<font color=...></font>` 更改字体颜色）。

  另外，Hexo 和 NexT 额外提供了一些基于 Nunjucks tags 语法的扩展功能，包括 iframe 对象、按钮、高亮、选项卡、内嵌 PDF 等功能，可参见 [Tag Plugins | Hexo](https://hexo.io/docs/tag-plugins) 和 [Tag Plugins | NexT](https://theme-next.js.org/docs/tag-plugins/)。

  {% note warning %}
  **注意**：应尽量避免将 Nunjucks tags 语法和较为复杂的 Markdown 语法（如数学公式、链接、图片、代码块等）嵌套使用，以防出现预期之外的问题。
  {% endnote %}

- 所有的博文均应置于 `source/_posts/` 文件夹内，博文需要引用的图片等资源（代码除外）需放于相同层级的同名文件夹中。

  例如对本篇文章来说，目录结构如下：

  ```text
  .
  └───source
      └───_posts
          ├───htc
          │   ├───edit-online-1.png
          │   ├───...
          │   └───workflow.svg
          └───htc.md
  ```

  本篇文章的文件位于 `source/_posts/htc.md`，所以本篇文章引用的图片都应置于 `source/_posts/htc/` 文件夹内。

  图片推荐使用 `.svg` 类型。若是由代码生成的图片（如 [gnuplot](http://www.gnuplot.info/)、[TikZ](https://github.com/pgf-tikz/pgf)、[Graphviz](https://graphviz.org/) 等），则应将代码一并上传。

- 在每篇文章的开头，需要撰写元数据（metadata）信息：

  ```yaml
  ---
  title: 如何参与 # 标题
  date: 2025-02-24 00:00:01 # 时间
  coauthor: # 作者列表
    - team
  categories: # 分类
  tags: # 标签列表
  mathjax: true # 如果文章不需要使用数学公式，则删除此行
  ---
  ```

- 用

  ```html
  <!-- more -->
  ```

  截断全文，防止文章在首页出现的部分过长。

- 用 `$<formula>$` 撰写行内公式，用

  ```tex
  $$
  <formula>
  $$
  ```

  撰写行间公式。例如：

  ```tex
  $$
  f(a)=\frac{1}{2\pi\mathrm{i}}\oint_{\Gamma}\frac{f(a)}{z-a}\operatorname{d}z.\tag{1}
  $$
  ```

  $$
  f(a)=\frac{1}{2\pi\mathrm{i}}\oint_{\Gamma}\frac{f(a)}{z-a}\operatorname{d}z.\tag{1}
  $$

  博客的数学公式渲染引擎为 [MathJax](https://www.mathjax.org)，需要注意的是 MathJax 和 LaTeX 之间有不少细节差别，而这些差别经常导致写出来的公式在二者之间不通用，具体可参考 [官方文档](https://docs.mathjax.org/en/latest/input/tex/differences.html)。

## 其他资料

- [Hexo 文档](https://hexo.io/docs/)
- [NexT 主题的文档](https://theme-next.js.org/docs/)
- [Markdown 语法表](https://www.markdownguide.org/cheat-sheet/)
