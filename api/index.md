---
# DO NOT TOUCH — Managed by doc writer
# ↑↑↑↑↑↑↑↑↑↑↑↑ 通过 doc writer 管理的，叫我别碰，但我还是碰了......（妈耶~）

ContentId: AD26EFB1-FFC6-4284-BAB8-F3BCB8294728
DateApproved: 3/7/2019

# Summarize the whole topic in less than 300 characters for SEO purpose
MetaDescription: Visual Studio Code has a rich extension API. Learn how to create your own extensions for VS Code.（ Visual Studio Code 拥有丰富的插件 API。学习如何为你的 VS Code 编写拓展插件。）
---

# Extension API

Visual Studio Code is built with extensibility in mind. From the UI to the editing experience, almost every part of VS Code can be customized and enhanced through the Extension API. In fact, many core features of VS Code are built as [extensions](https://github.com/Microsoft/vscode/tree/master/extensions) and use the same Extension API.

Visual Studio Code 是基于扩展性构建的。从 UI 到编辑体验，几乎 VS Code 的每一部分都可以通过 Extension API 定制或增强。事实上，VS代码的许多核心特性都是作为[extension](https://github.com/Microsoft/vscode/tree/master/extensions) 构建的，并且使用相同的 Extension API。

This documentation describes:
> 这份文档描述了

- How to build, run, debug, test and publish an extension
  > 如何构建、运行、调试、测试和发布一个 extension
- How to take advantage of VS Code's rich Extension API
  > 如何利用 VS Code 丰富的 Extension API
- Where to find guides and code samples to help get you started
  > 在哪里可以找到指南和示例代码来帮助您开始

If you are looking for published extensions, head to the [VS Code Extension Marketplace](https://marketplace.visualstudio.com/vscode).

如果您正在寻找已发布的扩展，请前往 [VS Code Extension Marketplace](https://marketplace.visualstudio.com/vscode).

## What can extensions do?（extension 能做什么？）

Here are some examples of what you can achieve with the Extension API:
> 以下是使用 Extension API 可以实现的一些示例

- Change the look of VS Code with a color or icon theme - [Theming](/api/extension-capabilities/theming)  
  > 用颜色或图标主题更改 VS Code 的外观
- Add custom components & views in the UI - [Extending the Workbench](/api/extension-capabilities/extending-workbench)
  > 在用户界面中添加自定义组件和视图
- Create a Webview to display a custom webpage built with HTML/CSS/JS - [Webview Guide](/api/extension-guides/webview)
  > 创建一个 Webview 来展示一个由 HTML/CSS/JS 构建的自定义页面
- Support a new programming language - [Language Extensions Overview](/api/language-extensions/overview)
  > 支持一门新的编程语言
- Support debugging a specific runtime - [Debugger Extension Guide](/api/extension-guides/debugger-extension)
  > 支持调试特定的运行时

If you'd like to have a more comprehensive overview of the Extension API, refer to the [Extension Capabilities Overview](/api/extension-capabilities/overview) page. [Extension Guides Overview](/api/extension-guides/overview) also includes a list of code samples and guides that illustrate various Extension API usage.

如果您想更全面地了解 Extension API，请参考 [Extension Capabilities Overview](/api/extension-capabilities/overview) 页面。[Extension Guides Overview](/api/extension-guides/overview) 还包括说明各种 Extension API 用法的代码示例和指南列表。


## How to build extensions? （如何构建一个扩展）

Building a good extension can take a lot of effort. Here is how each section of the API doc can help you with:  
> 构建一个良好的扩展需要付出很大的努力，下面这文档也许能够帮助到你：

- **Get Started** teaches fundamental concepts for building extensions with the [Hello World](https://github.com/Microsoft/vscode-extension-samples/tree/master/helloworld-sample) sample.
  > **Get Started** 通过 [Hello World](https://github.com/Microsoft/vscode-extension-samples/tree/master/helloworld-sample) 样例了解 extension 的基本概念
- **Working with Extensions** includes in-depth guides on various extension development topics, such as [publishing](/api/working-with-extensions/publishing-extension) and [testing](/api/working-with-extensions/testing-extension) extensions.
  > **Working with Extensions** 包括关于各种扩展开发主题的深入指南，例如 [publishing](/api/working-with-extensions/publishing-extension) and [testing](/api/working-with-extensions/testing-extension) 这两个扩展.
- **Extension Capabilities** dissects VS Code's vast API into smaller categories and points you to more detailed topics.
  > **Extension Capabilities** 将 VS Code 庞大的 API 分解成更小的类别，并指向更详细的主题
- **Extension Guides** includes guides and code samples that explains specific usages of VS Code Extension API.
  > **Extension Guides** 包括解释 VS Code Extension API 具体用法的指南和代码示例。
- **Language Extensions** illustrates how to add support for a programming language with guides and code samples.
  >  **Language Extensions** 演示如何添加对带有指南和代码示例的编程语言的支持
- **Advanced Topics** explains advanced concepts such as [Extension Host](/api/advanced-topics/extension-host) and [Proposed API](/api/advanced-topics/using-proposed-api).
  > **Advanced Topics** 解释高级概念，例如[Extension Host](/api/advanced-topics/extension-host) 与 [Proposed API](/api/advanced-topics/using-proposed-api).
- **References** contains exhaustive references for the [VS Code API](/api/references/vscode-api), [Contribution Points](/api/references/contribution-points), and many other topics.
  > **References** 为 [VS Code API](/api/references/vscode-api), [Contribution Points](/api/references/contribution-points) 以及其他许多主题提供了详尽的引用。

## Looking for help (寻求帮助）

If you have questions for extension development, try asking on:
> 如果您对扩展开发有疑问，请尝试询问:

- [Stack Overflow](https://stackoverflow.com/questions/tagged/visual-studio-code): There are [12k questions](https://stackoverflow.com/questions/tagged/visual-studio-code) tagged `visual-studio-code`, and over half of them already have answers. Search for your issue, ask questions, or help your fellow developers by answering VS Code extension development questions!
  > [Stack Overflow](https://stackoverflow.com/questions/tagged/visual-studio-code)： 这里有  [12k 个问题](https://stackoverflow.com/questions/tagged/visual-studio-code) 被打上了 `visual-studio-code` 的标签，并且超过一半的问题已经有了回答。搜索您的问题，提出问题，或者通过回答 VS Code 扩展的相关开发问题来帮助各位开发者吧！
- [Gitter Channel](https://gitter.im/Microsoft/vscode) and [VS Code Dev Slack](https://join.slack.com/t/vscode-dev-community/shared_invite/enQtMjIxOTgxNDE3NzM0LWU5M2ZiZDU1YjBlMzdlZjA2YjBjYzRhYTM5NTgzMTAxMjdiNWU0ZmQzYWI3MWU5N2Q1YjBiYmQ4MzY0NDE1MzY): Public chatroom for extension developers. Some VS Code team members chime in conversations.
  > [Gitter Channel](https://gitter.im/Microsoft/vscode) 与 [VS Code Dev Slack](https://join.slack.com/t/vscode-dev-community/shared_invite/enQtMjIxOTgxNDE3NzM0LWU5M2ZiZDU1YjBlMzdlZjA2YjBjYzRhYTM5NTgzMTAxMjdiNWU0ZmQzYWI3MWU5N2Q1YjBiYmQ4MzY0NDE1MzY): 面向扩展插件开发者的聊天室，与 VS Code 的团队成员交流

To provide feedback on the documentation, create new issues at [Microsoft/vscode-docs](https://github.com/Microsoft/vscode-docs/issues).  
> 为文档提供反馈，在 [Microsoft/vscode-docs](https://github.com/Microsoft/vscode-docs/issues) 创建新的 issues。

If you have extension questions that you cannot find an answer for, or issues with VS Code Extension API, please open new issues at [Microsoft/vscode](https://github.com/Microsoft/vscode/issues).  
> 如果你有一些关于扩展 或 VS Code Extension API 的问题无法找到答案，请在 [Microsoft/vscode](https://github.com/Microsoft/vscode/issues) 下激活 issues
