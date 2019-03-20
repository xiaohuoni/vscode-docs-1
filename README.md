<p align="center">
  <img alt="vscode logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Visual_Studio_Code_1.18_icon.svg/1200px-Visual_Studio_Code_1.18_icon.svg.png" width="100px" />
  <h1 align="center">Visual Studio Code Documentation</h1>
</p>

You've found the Visual Studio Code documentation GitHub repository, which contains the content for the [Visual Studio Code documentation](https://code.visualstudio.com/docs).

您已经找到了 Visual Studio Code文档 GitHub 存储库, 其中包含 [Visual Studio Code documentation](https://code.visualstudio.com/docs)的内容。

Topics submitted here will be published to the [Visual Studio Code](https://code.visualstudio.com) portal.

此处提交的主题将发布到[Visual Studio Code documentation](https://code.visualstudio.com/docs)门户网站。

If you are looking for the VS Code product GitHub repository, you can find it [here](https://github.com/Microsoft/vscode).

如果您正在寻找 VS Code 产品 GitHub 存储库, 您可以在[这里](https://github.com/Microsoft/vscode)找到它。

## Index

1. [About Visual Studio Code](#visual-studio-code)
2. [Feedback](#feedback)
3. [Documentation Issues](#documentation-issues)
4. [Contributing to the documentation](#contributing)
5. [Publishing](#publishing)

## Visual Studio Code

[VS Code](https://code.visualstudio.com/) is a lightweight source code editor and powerful development environment for building and debugging modern web and cloud applications. It is free and available on your favorite platform - Linux, macOS, and Windows.

[VS Code](https://code.visualstudio.com/) 是一个轻量级的源代码编辑器和强大的开发环境, 用于构建和调试现代 web 和云应用程序。它是免费的, 可在您最喜爱的平台上 - Linux, macOS 和 Windows。

If you landed here looking for other information about VS Code, head over to [our website](https://code.visualstudio.com) for additional information.

如果您在这里找到有关 VS 代码的其他信息, 请前往[我们的网站](https://code.visualstudio.com)了解更多信息。

## Feedback

If you want to give documentation feedback, please use the feedback control located at the bottom of each documentation page.

如果要提供文档反馈, 请使用位于每个文档页面底部的反馈控件。

## Documentation Issues

To enter documentation bugs, please create a [new GitHub issue](https://github.com/Microsoft/vscode-docs/issues). Please check if there is existing issue first.

要报告文档错误, 请创建一个 [new GitHub issue](https://github.com/Microsoft/vscode-docs/issues)。请先检查是否存在问题。

If you think the issue is with the VS Code product itself, please enter issues in the VS Code product repo [here](https://github.com/Microsoft/vscode/issues).

如果您认为问题出在 VS 代码产品本身, 请在 VS Code 产品存储库中输入问题[here](https://github.com/Microsoft/vscode/issues).

## Contributing

To contribute with new topics / information or make changes to existing documentation, please read the [Contributing Guideline](./CONTRIBUTING.md#contributing).

要提供新的主题/信息或对现有文档进行更改, 请阅读[Contributing Guideline](./CONTRIBUTING.md#contributing)

### Workflow

The two suggested workflows are:
建议的两个工作流是:

- For small changes, use the "Edit" button on each page to edit the Markdown file directly on GitHub.
- 对于小的更改, 使用 "编辑" 按钮上的每个页面直接编辑标记文件在 GitHub 上。
- If you plan to make significant changes or preview the Markdown files in VS Code, [clone](#cloning) the repo to [edit and preview](https://code.visualstudio.com/docs/languages/markdown) the files directly in VS Code.
- 如果您计划在 VS 代码中进行重大更改或预览标记文件, [clone](#cloning) 将存储库直接放到 VS 代码中的[edit and preview](https://code.visualstudio.com/docs/languages/markdown) 。

![Markdown Preview Button](images/MDPreviewButton.png)

### Cloning

We have adopted [Git LFS](https://git-lfs.github.com/) to store the images in this repo. Bare `git clone` will take 1.4GB+, and we recommend the following setup:
我们已经采用 [Git LFS](https://git-lfs.github.com/)  将图像存储在此存储库中。`git clone` 将采用 1.4 gb+, 我们建议使用以下设置:

- Install [Git LFS](https://git-lfs.github.com/).
- 安装[Git LFS](https://git-lfs.github.com/)
- `git lfs install`. You only need to run this once.
- `git lfs install`. 您只需运行此一次
- `GIT_LFS_SKIP_SMUDGE=1 git clone https://github.com/Microsoft/vscode-docs.git`. This only downloads text files that amount to ~16MB.
- `GIT_LFS_SKIP_SMUDGE=1 git clone https://github.com/Microsoft/vscode-docs.git`.这只下载相当于 ~ 16MB 的文本文件。
- `git lfs pull -I <PATTERN>`, where [`<PATTERN>`](https://github.com/git-lfs/git-lfs/blob/master/docs/man/git-lfs-fetch.1.ronn#include-and-exclude) is a string of comma-separated globs. For example:
    - `git lfs pull -I "docs/nodejs"`. Only download images in `docs/nodejs`.
    - `git lfs pull -I "release-notes/images/1_3*/*"`. Only download images in latest release notes.
- Alternatively, use `git config lfs.fetchinclude "docs"` so future `git lfs pull` only pulls images in `docs`.

The history of this repo before we adopt LFS can be found at [microsoft/vscode-docs-archive](https://github.com/Microsoft/vscode-docs-archive).

在我们采用 LFS 之前, 可以在 [microsoft/vscode-docs-archive](https://github.com/Microsoft/vscode-docs-archive) 中找到历史。
## Publishing

Steps for how to publish documentation changes can be found [here](https://github.com/Microsoft/vscode-website#publishing-a-documentation-change) in the (private) repository of the VS Code website.
如何发布文档更改的步骤可在 VS Code 网站的 (私人) 存储库中找到[here](https://github.com/Microsoft/vscode-website#publishing-a-documentation-change)
