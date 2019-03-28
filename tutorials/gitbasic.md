# git 基础操作

本页主要说明参与翻译所需的 git 命令行的基础操作，如果你想学习更多技能：

* 关于客户端操作，请参考该客户端的具体文档。
* 关于 git 命令行完整帮助，请查阅 `man git` 及 `git help command`。
* 更多 git 概念及技能请参考 [Pro Git](https://git-scm.com/book/zh/v2)。

## 基础配置

### 用户信息

使用 git 前需要先配置用户名及邮箱等基础信息，示例如下。

```
git config --global user.name "张三"
git config --global user.email "zhangsan@example.com"
```

**注意！**以上命令会设置系统全局的 git 信息，建议在 clone 仓库后进入项目目录中使用以下命令设置：

```
git config user.name "张三"
git config user.email "zhangsan@example.com"
```

### SSH key 及 GPG key（可选）

请参考 [GitHub SSH 帮助页面](https://help.github.com/en/articles/connecting-to-github-with-ssh)进行设置 ssh key，这样可以在每次 push 时免除输入密码。

GPG 可进行加密及数字签名，请参考 [GitHub GPG key 帮助页面](https://help.github.com/en/articles/managing-commit-signature-verification)进行设置。

## clone 仓库

在<ruby>复刻<rt>fork</rt></ruby> [LCTT/TranslateProject](https://github.com/LCTT/TranslateProject) <ruby>仓库<rt>repository</rt></ruby>后，将自己的仓库 clone 至本地。

```
git clone git@github.com:$YOUR_GITHUB_ID/TranslateProject.git
```

如果 clone 速度比较慢可添加 `--depth N` 参数进行<ruby>浅层克隆<rt>shallow clone</rt></ruby>，N 表示仅保留最新的 N 次 commit。如：

```
git clone --depth 1 git@github.com:$YOUR_GITHUB_ID/TranslateProject.git
```

这样会把仅包含最后一次提交的完整文件列表 clone 下来，如果需要所有的 commit，可以到项目目录中执行 `git fetch --unshallow` 获取。

## 分支操作

一般来说只需要在默认的 master 分支上开始翻译即可。<ruby>分支<rt>branch</rt></ruby>是 git 最核心的设计之一，灵活且强大，如果你需要使用分支，可以参考以下建议。

基于当前状态创建一个名为 `my_branch` 的新分支：

```
git checkout -b my_branch
```

也可以基于某个 commit 创建（`$COMMIT_ID` 可以是一个 commit ID，远程分支名或任意有效<ruby><rt>符号标识</rt>symblolic identifier</ruby>）：

```
git checkout -b my_branch $COMMIT_ID
```

切换至某分支可使用 `git checkout some_branch`，切换回上次所在的分支可使用 `git checkout -`。更多分支操作请参考 `git help branch`，`git help remote` 及 `git help checkout`。

## 提交变更

当你认为工作进度应该阶段性保存时应该进行<ruby>提交<rt>commit</rt></ruby>，提交后会将你的变更存入本在 git 数据库。首先检查当前的变更是否满意，满意的话用 `git add xxx` 添加修改的文件，然后进行提交。

```
git commit
```

运行这个命令后会打开一个默认的编辑器让你填写这次变更的概要信息。一般只填写第一行标题就可以，如果标题不足以描述清楚此次变更，请隔一个空行后描述变更的正文。有兴趣可以了解 [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)。

你也可以使用 `git commit -m "my commit message"` 编写提交信息，如果你对自己的操作足够自信的话。不过还是推荐使用在编辑器中编辑 commit message，这种方式相对更稳妥一些。你可以使用 `git config --global core.editor $YOUR_EDITOR` 来设置一个你熟悉的编辑器作为 git 默认的编辑器。

有时有必要修改提交信息，比如可以使用 `git commit --amend` 来修改上次提交信息，可以修改的地方很多，包括用户名，邮箱，时间等，更多信息请参考 `git help commit`。

## 推送到远程

前面所提及操作的影响范围都仅限于本地，当你认为本地的状态已满意，可以<ruby>推送<rt>push</rt></ruby>到远程以发便起<ruby>拉取请求（PR）<rt>pull request</rt></ruby>将你的贡献合并到<ruby>上游<rt>upstream</rt></ruby>仓库。

```
git push
```

当你在 master 分支上工作时，这条简单的命令就够用了。当你在某个分支上工作时，需要注意向<ruby>远程分支<rt>remote branch</rt></ruby> 推送时要指定目标分支：

```
git push origin my_branch
```

## 其它

以下命令完整帮助信息请使用 `git help command` 获取。

### `git status`

这应该是你用的最多的一条 git 命令，也是最没有危险的一条命令。它会显示工作区的当前状态，可以给你很多提示。

### `git log`

查看提交历史，该命令有超多选项及选项组合。

### `git show`

查看上次提交信息，可以指定某些 commit 及任意有效标识符。

### `git diff`

该命令可以在任意两种状态或 commit 之间进行差异对比，可以通过 `git config --global diff.tool $BETTER_DIFF_TOOL` 来设置一个更专业的 diff 工具，然后用 `git difftool` 来查看并修改差异信息。

### `git fetch`

获取远程更新，但并不将远程更新合并到本地。

### `git pull`

获取远程更新并将远程更新合并到本地。
