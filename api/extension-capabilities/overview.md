---
# DO NOT TOUCH — Managed by doc writer
ContentId: d22675fc-6609-43f2-a66b-8f2a52597195
DateApproved: 3/7/2019
批准日期：3/7/2019
# Summarize the whole topic in less than 300 characters for SEO purpose
# 为达到搜索引擎优化（SEO）的目的，用300个以内字符总结整个主题
MetaDescription: Learn the details of what's possible with Visual Studio Code's rich extension (plug-in) API.
MetaDescription:了解Visual Studio Code丰富扩展(插件)API可能性的详细信息
---

# Extensions Capabilities Overview

# 扩展功能概述

Visual Studio Code offers many ways for extensions to extend its capabilities. It can sometimes be hard to find the right [Contribution Points](/api/references/contribution-points) and [VS Code API](/api/references/vscode-api) to use. This topic splits extension capabilities into a few categories. Each category describes:

Visual Studio Code 为扩展其功能提供了许多扩展方法。有时候很难找到正确的[贡献点](/api/references/贡献点)和[VS Code API](/api/references/vscode-api)来使用。本主题将扩展功能分为几个类别。每个类别描述如下:

- Some functionalities your extension could use
- 你的插件可以使用的一些功能
- Links to more detailed topics for using these functionalities
- 为使用这些功能，连接更多详细主题
- A few extension ideas
- 一些扩展的构想

However, we also impose [restrictions](#restrictions) upon extensions to ensure the stability and performance of VS Code. For example, extensions cannot access the DOM of VS Code UI.

但是，我们也对扩展施加了[限制](#restrictions) ，以确保 VS Code 的稳定性和性能。例如，扩展不能访问 VS Code UI 的 DOM。

## Common Capabilities

## 通用功能

[Common Capabilities](./common-capabilities) are core pieces of functionality that you can use in any extension.
[公共功能](./common-capabilities)是你在任何扩展中都可以使用的核心功能。

Some of these capabilities include:
这些功能当中包括：

- Registering commands, configurations, keybindings, or context menu items.
- 注册命令、配置、快捷键或上下文菜单项。
- Storing workspace or global data.
- 存储工作区或全局的数据。
- Displaying notification messages.
- 显示通知消息。
- Using Quick Pick to collect user input.
- 使用快速拾取功能收集用户输入信息
- Open the system file picker to let users select files or folders.
- 打开系统文件选择器，让用户选择文件或文件夹。
- Use the Progress API to indicate long-running operations.
- 使用 Progress API 指示长时间运行的操作。

## Theming

## 主题

[Theming](./theming) controls the look of VS Code, both the colors of source code in the editor and the colors of the VS Code UI. If you've ever wanted to make it look like you're coding the Matrix by making VS Code different shades of green, or just wanted to create the ultimate, minimalist grayscale workspace, then themes are for you.
[主题](./theming) 控制 VS Code 的外观，包括编辑器中源代码的颜色和 VS Code UI 的颜色。如果你想让它看起来像是通过不同深浅的绿色所编码矩阵，或者只是想创建一个终极的、极简的灰度工作区，那么主题正是你所需要的。

**Extension Ideas**
**扩展构想**

- Change colors of your source code.
- 更改源代码的颜色
- Change colors of the VS Code UI.
- 更改 VS Code UI 的颜色
- Port an existing TextMate theme to VS Code.
- 将现有的 TextMate 主题移植到 VS Code 中
- Add custom file icons.
- 添加自定义文件图标

## Declarative Language Features

声明性语言特性

[Declarative Language Features](/api/language-extensions/overview#declarative-language-features) adds basic text editing support for a programming language such as bracket matching, auto-indentation and syntax highlighting. This is done declaratively, without writing any code. For more advanced language features, like IntelliSense or debugging, see [Programmatic Language Features](#programmatic-language-features).
[声明性语言特性](/api/language-extensions/overview#declarative-language-features) 为编程语言添加了基本的文本编辑功能支持，比如括号匹配、自动缩进和语法突出显示。这是声明性的，不需要编写任何代码。更高级的语言特性，如智能感知或调试，请参见[编程语言特性](#programmatic-language-features)。

**Extension Ideas**
**扩展构想**

- Bundle common JavaScript snippets into an extension.
- 将常见的 JavaScript 片段捆绑到扩展中
- Tell VS Code about a new programming language.
- 告知 VS Code 一种新的编程语言
- Add or replace the grammar for a programming language.
- 为编程语言添加或替换语法
- Extend an existing grammar with grammar injections.
- 通过语法注入扩展现有语法
- Port an existing TextMate grammar to VS Code.
- 将现有的 TextMate 语法移植到 VS Code 中

## Programmatic Language Features

## 编程语言特性

[Programmatic Language Features](/api/language-extensions/overview#programmatic-language-features) add rich programming language support such as Hovers, Go to Definition, diagnostic errors, IntelliSense and CodeLens. These language features are exposed through the [`vscode.languages.*`](/api/references/vscode-api#languages) API. An extension can either use these API directly, or write a Language Server and adapt it to VS Code using the VS Code [Language Server library](https://github.com/Microsoft/vscode-languageserver-node).

[编程语言特性](/api/language-extensions/overview#programmatic-language-features) 添加了丰富的编程语言支持，如 Hovers、转到定义、诊断错误、智能感知和 CodeLens。这些语言特性通过[`vscode.languages.*`](/api/references/vscode-api#languages)API 显示。扩展可以直接使用这些 API，或者编写一个语言服务器，并使用 VS Code[语言服务器库](https://github.com/Microsoft/vscode-languageserver-node) 改编 API。

Although we provide a listing of [language features](/api/language-extensions/programmatic-language-features) and their intended usage, nothing prevents you from using these API creatively. For example, CodeLens and Hovers are a great way to present additional information inline, while diagnostic errors can be used to highlight spelling or code style errors.

尽管我们提供了[语言特性](/api/语言扩展/编程语言特性)及其预期用途的列表，但是并没有阻止你创造性地使用这些 API。例如，CodeLens 和 Hovers 是内联显示附加信息的好方法，而诊断错误可以用来突出显示拼写或代码样式的错误。

**Extension Ideas**
**扩展构想**

- Add hovers that show sample usage of an API.
- 添加显示 API 使用示例的 hovers
- Report spelling or linter errors in source code using diagnostics.
- -使用诊断来报告源代码中的拼写或 linter 错误
- Register a new code formatter for HTML.
- 为 HTML 注册一个新的代码格式化程序
- Provide rich, context-aware IntelliSense.
- 提供丰富的、感知上下文的智能感知
- Add folding, breadcrumbs and outline support for a language.
- 为语言添加折叠，breadcrumbs 和大纲支持

## Workbench Extensions

## 工作台扩展

[Workbench Extensions](./extending-workbench) extend the VS Code Workbench UI. Add new right-click actions to the File Explorer, or even build a custom explorer using VS Code's [TreeView](/api/extension-guides/tree-view) API. And if your extension needs a fully customized user interface, use the [Webview API](/api/extension-guides/webview) to build your own document preview or UI using standard HTML, CSS, and JavaScript.

[工作台扩展](./extending-workbench) 扩展了 VS Code Workbench UI。文件资源管理器添加新的右键单击操作，或者使用 VS Code 的[树视图](/api/extension-guides/tree-view) API 构建自定义资源管理器。如果你的扩展需要完全自定义的用户界面，使用[Webview API](/api/extension-guides/webview)构建你自己的文档预览或使用标准 HTML、CSS 和 JavaScript 构建 UI。

**Extension Ideas**
**扩展构想**

- Add custom context menu actions to the File Explorer.
- 在文件资源管理器中添加自定义上下文菜单操作
- Create a new, interactive TreeView in the Side Bar.
- 在侧边栏中创建一个新的交互式树视图
- Define a new Activity Bar view.
- 定义一个新的活动栏视图
- Show new information in the Status Bar.
- 在状态栏中显示新信息
- Render custom content using the `WebView` API.
- 使用`WebView`API 呈现自定义内容。
- Contribute Source Control providers.
- 贡献源代码控制提供者

## Debugging

## 调试

You can take advantage of VS Code's [Debugging](/docs/editor/debugging) functionality by writing [Debugger Extensions](/api/extension-guides/debugger-extension) that connect VS Code's debugging UI to a specific debugger or runtime.

你可以利用 VS Code 的[调试](/docs/editor/debugging) 功能，具体是通过编写[调试器扩展](/api/extension-guides/debugger-extension)将 VS Code 的调试 UI 连接到特定的调试器或运行上。

**Extension Ideas**
**扩展构想**

- Connect VS Code's debugging UI to a debugger or runtime by contributing a [Debug Adapter implementation](https://microsoft.github.io/debug-adapter-protocol/implementors/adapters/).
- 通过提供一个[调试适配器实现](https://microsoft.github.io/debug-adapter-protocol/implementors/adapters/) 将 VS Code 的调试 UI 连接到调试器或运行时间
- Specify the languages supported by a debugger extension.
- 指定调试器扩展所支持的语言
- Provide rich IntelliSense and hover information for the debug configuration attributes used by the debugger.
- 为调试器使用的调试配置属性提供丰富的智能感知和 hover 信息
- Provide debug configuration snippets.
- 提供调试配置片段

On the other hand, VS Code also offers a set of [Debug Extension API](/api/references/vscode-api#debug), with which you can implement debug-related functionality on top of any VS Code debugger, in order to automate users' debugging experience.

另一方面，VS Code 还提供了一组[调试扩展 API](/api/references/vscode-api#debug)，你可以使用它在任何 VS Code 调试器之上执行与调试相关的功能，以便自动化用户的调试体验

**Extension Ideas**
**扩展构想**

- Start debug sessions based on dynamically created debug configurations.
- 基于动态创建的调试配置启动调试会话
- Track the lifecycle of debug sessions.
- 跟踪调试会话的生命周期
- Create and manage breakpoints programmatically.
- 以编程方式创建和管理断点。

<!-- Add below content back after writing ./extending-core-functionalities.md  -->
<!-- 编写完后将以下内容添加回去 ./ 扩展-核心-功能.md  -->
<!-- ## Core Extensions
<!-- ## 核心扩展

[Core Extensions](extending-core-functionalities) are for very advanced users. These let you build a custom back end for many of VS Code's low-level functionality. For example, the `FileSystem` API can be used to support working with files over FTP or other protocols. Core extensions typically work transparently from a user's point of view.

[核心扩展](扩展-核心-功能)适用于高级用户。你可以为许多VS Code的低级别功能构建自定义后端。例如，`文件系统`API可用于支持通过FTP或其他协议处理文件。从用户的角度看，核心扩展通常透明化工作。

**Extension Ideas**
**扩展构想**

- Add support for working with remote files over FTP or SFTP.
- 添加对通过FTP或SFTP处理远程文件的支持
- Register new source control provider, such as Mercurial.
- 注册新的源代码控制提供程序，如Mercurial
- Implement a custom file search provider. -->

- 执行自定义文件搜索提供程序。-->

## Restrictions

## 限制

There are certain restrictions we impose upon extensions. Here are the restrictions and their purposes.

我们对扩展施加了一些限制。限制的具体方面及其限制的目的如下

### No DOM Access

### 无法访问 DOM

Extensions have no access to the DOM of VS Code UI. You **cannot** write an extension that applies custom CSS to VS Code or adds a HTML element to VS Code UI.

扩展不能访问 VS Code UI 的 DOM。你**不能**编写将自定义 CSS 应用于 VS Code 或将 HTML 元素添加到 VS Code UI 的扩展。

At VS Code, we're continually trying to optimize use of the underlying web technologies to deliver an always available, highly responsive editor and we will continue to tune our use of the DOM as these technologies and our product evolve. To ensure that extensions cannot interfere with the stability and performance of VS Code, and that we can continue to improve the DOM of VS Code without breaking existing extensions, we run extensions in an [Extension Host](/api/advanced-topics/extension-host) process and prevent direct access to the DOM.

在 VS Code 中，我们不断尝试优化底层 web 技术的使用，提供一个始终可用、响应性高的编辑器，并且随着这些技术和产品的发展，我们将继续调整 DOM 的使用。为了确保扩展不会干扰 VS Code 的稳定性和性能，以及我们可以在不破坏现有扩展的情况下继续改进 VS Code 的 DOM，我们在[扩展主机](/api/advanced-topics/extension-host) 进程中运行扩展，并防止直接访问 DOM。
