# 通过 Web 界面进行翻译

在 web 上操作，步骤如下：

## 准备工作

首先，你需要注册 [GitHub](https://github.com/)，具体步骤此处不赘述。

如果已有 GitHub 账户，请登录。

## 将 TranslateProject 的主仓库复刻到你名下

根据你是初次翻译还是已经进行过翻译，情况略有不同：

### 初次翻译

如果你尚未参与过本项目的翻译活动，请按如下步骤：

进入 LCTT 的仓库主页：[https://github.com/LCTT/TranslateProject](https://github.com/LCTT/TranslateProject) ，点击右上角的 “Fork” 按钮将仓库<ruby>复刻<rt>fork</rt></ruby>到自己名下。

![点击右上角的 “Fork” 按钮](../images/guide_images/fork_repo1.png)

![复刻过程中](../images/guide_images/fork_repo2.png)

成功后，你就有一个自己的 TranslateProject 仓库了，在这个仓库你可以进行任何操作。在遇到棘手的问题时，你甚至可以删除掉你的这个本地仓库，重新复刻（如果你有任何需要保留的修改，请另行备份）。

![你复刻的仓库](../images/guide_images/fork_repo3.png)

### 再次翻译

如果你已经翻译过一篇或更多篇，你需要在再次翻译前确保你名下的仓库是更新的。在 GitHub 网站上是通过反向的 PR 进行的。

首先，访问你已经复刻到**你名下的仓库**。然后点击你仓库首页的 “New pull request” 按钮：

![点击 “New pull request” 按钮](../images/guide_images/update_repo1.jpg)

在显示 “Comparing changes” 页面，点击右侧如图所示的下拉菜单，选择 “LCTT/TranslateProject”：

![选择 “LCTT/TranslateProject”](../images/guide_images/update_repo2.jpg)

这时该页面会刷新，并显示没有差异，请点击右上角的 “compare across forks” 链接：

![点击 “compare cross forks” 链接](../images/guide_images/update_repo3.jpg)

点击后，会重新出现下拉菜单，在左侧如图所示的下拉列表中，选择你复刻的仓库名称：

![选择你复刻的仓库名称](../images/guide_images/update_repo4.jpg)

页面刷新后，会出现创建 PR 的页面，请点击 “Create new pull request” 按钮：

![点击 “Create new pull request” 按钮](../images/guide_images/update_repo5.jpg)

在出现的输入框中输入说明性文字，并点击 “Create pull request” 按钮：

![点击 “Create pull request” 按钮](../images/guide_images/update_repo6.jpg)

创建了 PR 之后，会直接显示一个页面，该 PR 可以直接合并，点击 “Merge pull request” 按钮从 LCTT 主仓库合并最新更新到你名下的仓库中：

![合并 PR](../images/guide_images/update_repo7.jpg)

这样，你名下的仓库就和 LCTT 的主仓库同步了，可以继续申请和翻译文章了。

## 翻译申请

进入你复刻的 LCTT 仓库，从 `sources` 目录中挑选你所喜欢，也擅长的文章。文章分两类：`talk` 和 `tech`，`talk` 的文章偏议论，`tech` 的文章都是技术干货。

![选择文章分类](../images/guide_images/tran1.jpg)

进入子目录后，点击一篇没有被人申领的文章。所有已被申领的文章的头部都应该有相应的申请信息。你也可以直接选择那些在列表中显示“选题：……”的信息——这些代表该文章选题后从未有人翻译过。

![选择选题](../images/guide_images/tran2.jpg)

显示该文章内容后，如果是你所喜欢、内容难度也符合你的能力，请点击文章右上角的”铅笔“按钮，编辑该文章。

![编辑](../images/guide_images/tran3.jpg)

我们目前并存着两种文章模板：

- 没有头部元信息的旧模板：请在文章的头部加入 `你的_GitHub_ID is translating`。
- 有头部元信息的新模板：请修改头部元信息 `[#]: translator: ( )` 中的 `( )`，在其中写入你的 GitHub ID。

![申领](../images/guide_images/tran4.jpg)

然后在页面底部的提交框输入相应的说明文字，并点击 “Commit changes” 来提交申请：

![提交改变](../images/guide_images/tran5.jpg)

最后，回到你的仓库首页，点击 “New pull request” 按钮，将你在自己的代码库进行的操作合并到 LCTT 的主仓库，提交 PR。

![创建 PR](../images/guide_images/tran_pr1.jpg)

一个 PR 会包含你的仓库当前的所有操作，只要和主仓库不一样都会提交，所以，你每完成一个操作（申领原文、提交译文）就要提交一次 PR，在当前 PR 没有被合并之前不要发起新的 PR。

![创建 PR](../images/guide_images/tran_pr2.jpg)

PR 里面写好说明，指出你当前的操作是什么：申领原文、提交译文等。

![提交 PR](../images/guide_images/tran_pr3.jpg)

操作成功。这时你的 PR 正在进行 CI 检查是否合规。
![PR 的 CI 检查](../images/guide_images/tran_pr4.jpg)

稍候片刻，CI 检查通过后，一般就可以等待管理员合并你的 PR。如果提交的 PR 有问题，管理员会提醒你（GitHub 通知或者 QQ 群），然后再做修改重新发起 PR。

![PR 的 CI 检查通过](../images/guide_images/tran_pr5.jpg)

然后，你就可以自行进行翻译了。

## 提交翻译

翻译完成之后，再次编辑该文章，修改内容为译文内容，并修改文末的译者 ID 为你的 GitHub ID。

然后要修改（`sources` 下）原文的路径为（`translated` 下）译文路径。首先点击文章页面上部的文件名栏，并将输入光标置于第一个字母之前：

![将输入光标置于第一个字母之前](../images/guide_images/tran_ren1.jpg)

然后按退格键，该输入框会“吃掉”前面的目录路径：

![按退格键](../images/guide_images/tran_ren2.jpg)

由于我们需要将译文移动到其两级父目录之外，我们继续移动输入光标到该输入框最左端，再次按下退格键“吃掉”目录：

![再按退格键](../images/guide_images/tran_ren3.jpg)

然后修改 `sources` 为 `translated`，然后输入 `/` 来建立目录：

![输入 / 来建立目录](../images/guide_images/tran_ren4.jpg)

然后移动到子目录名（如 `tech` ）后输入 `/` 来建立目录：

![输入 / 来建立目录](../images/guide_images/tran_ren5.jpg)

最后点击该页面尾部的 “Commit changes” 来提交该译文的修改。

然后按照前面所述，从项目首页创建 PR 提交到 LCTT 的 TranslateProject 主库。

整个翻译的流程就如上所述。在实际操作中，如果遇到问题，欢迎在 QQ 群提问。
