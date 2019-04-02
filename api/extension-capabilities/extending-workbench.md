---
# DO NOT TOUCH — Managed by doc writer
# 请勿更改-这个文档由作者管理
ContentId: e0d5bd37-f020-4235-ad81-c977baaeb24f
DateApproved: 3/7/2019
批准日期：3/7/2019
# Summarize the whole topic in less than 300 characters for SEO purpose
# 为达到搜索引擎优化（SEO）的目的，用300个以内字符总结整个主题
MetaDescription: Explain how to extend Visual Studio Code's workbench area with custom UI components
MetaDescription: 解释如何使用自定义UI组件扩展Visual Studio code的工作台区域
---

# Extending Workbench

# 扩展工作台

"Workbench" refers to the overall Visual Studio Code UI that encompasses the following UI components:

"工作台" 指的是包含以下 UI 组件的整个 Visual Studio Code UI:

- Title Bar
- 标题栏
- Activity Bar
- 活动栏
- Side Bar
- 侧栏
- Panel
- 面板
- Editor Group
- 编辑器组
- Status Bar
- 状态栏

VS Code provides various APIs that allow you to add your own components to the Workbench. For example, in the image below:

VS Code 提供各种 API，允许你将自己的组件添加到工作台上。例如，如下图所示:

![workbench-contribution](images/extending-workbench/workbench-contribution.png)

- Activity Bar: The [Azure App Service extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azureappservice) adds a [View Container](#view-container)
- 活动栏：[Azure App Service extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azureappservice) 添加一个[视图容器](#view-container)
- Side Bar: The built-in [NPM extension](https://github.com/Microsoft/vscode/tree/master/extensions/npm) adds a [Tree View](#tree-view) to the Explorer View
- -侧栏:内置的[NPM 扩展](https://github.com/Microsoft/vscode/tree/master/extensions/npm)向资源管理器视图添加了一个[树视图](#tree-view)
- Editor Group: The built-in [Markdown extension](https://github.com/Microsoft/vscode/tree/master/extensions/markdown-language-features) adds a [Webview](#webview) next to other editors in the Editor Group
- 编辑器组:内置的[Markdown 扩展](https://github.com/Microsoft/vscode/tree/master/extensions/markdown-language-features)在编辑器组中的其他编辑器旁边添加了一个[Web 视图](#webview)
- Status Bar: The [VSCodeVim extension](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim) adds a [Status Bar Item](#status-bar-item) in the Status Bar
- 状态栏:[VSCodeVim 扩展](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)在状态栏中添加一个[状态栏项](#status-bar-item)

## Views Container

## 视图容器

With the [`contributes.viewsContainers`](/api/references/contribution-points#contributes.viewsContainers) Contribution Point, you can add new Views Containers that display next to the five built-in Views Containers. Learn more at the [Tree View](/api/extension-guides/tree-view) topic.

## Tree View

## 树视图

With the [`contributes.views`](/api/references/contribution-points#contributes.views) Contribution Point, you can add new Views that display in any of the View Containers. Learn more at the [Tree View](/api/extension-guides/tree-view) topic.

使用[`contributes.views`](/api/references/contribution-points#contributes.views) 贡献点，你可以将新视图添加并显示在任何视图容器中。更多信息在[树视图](/api/extension-guides/tree-view)主题中。

## Webview

## Web 视图

Webviews are highly customizable views built with HTML/CSS/JavaScript. They display next to text editors in the Editor Group areas. Read more about Webview in the [Webview Guide](/api/extension-guides/webview).

Webview 是用 HTML/CSS/JavaScript 构建的可定制视图。它们显示在编辑器组区域的文本编辑器旁。阅读更多关于 Webview 的信息请见[Webview 指南](/api/extension-guides/webview)

## Status Bar Item

## 状态栏项

Extensions can create custom [`StatusBarItem`](/api/references/vscode-api#StatusBarItem) that display in the Status Bar. Status Bar Items can show text and icons and run commands on click events.

插件可以在状态栏中创建并显示自定义[`状态栏项`](/api/references/vscode-api#StatusBarItem)。状态栏项可以显示文本和图标，并单击运行命令。

- Show text and icons
- 显示文本和图标
- Run a command on click
- 单击运行命令

  A Status Bar extension sample can be found [here](https://github.com/Microsoft/vscode-extension-samples/tree/master/statusbar-sample).

  在[here](https://github.com/Microsoft/vscode-extension-samples/tree/master/statusbar-sample)可以找到状态栏的扩展示例。
