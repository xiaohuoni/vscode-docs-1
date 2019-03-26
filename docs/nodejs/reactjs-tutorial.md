---
Order: 5
Area: nodejs
TOCTitle: React Tutorial
ContentId: 2dd2eeff-2eb3-4a0c-a59d-ea9a0b10c468
PageTitle: React JavaScript Tutorial in Visual Studio Code
DateApproved: 3/7/2019
MetaDescription: React JavaScript tutorial showing IntelliSense, debugging, and code navigation support in the Visual Studio Code editor.
MetaSocialImage: /assets/images/nodejs_javascript_vscode.png
---
# Using React in Visual Studio Code

[React](https://facebook.github.io/react/) is a popular JavaScript library developed by Facebook for building web application user interfaces. The Visual Studio Code editor supports React.js IntelliSense and code navigation out of the box.
[React](https://facebook.github.io/react/) 是 Facebook 开发的一个流行的 JavaScript 库，用于构建 Web 应用程序用户界面。 Visual Studio Code 编辑器支持 React.js IntelliSense和开箱即用的代码导航。

![welcome to react](images/reactjs/welcome-to-react.png)

## Welcome to React

We'll be using the `create-react-app` [generator](https://facebook.github.io/react/docs/installation.html#creating-a-new-application) for this tutorial. To install and use the generator as well as run the React application server, you'll need [Node.js](https://nodejs.org/) JavaScript runtime and [npm](https://www.npmjs.com/) (Node.js package manager) installed. npm is included with Node.js which you can download and install from [here](https://nodejs.org/en/download/).

我们将在本教程中使用 `create-react-app` [generator](https://facebook.github.io/react/docs/installation.html#creating-a-new-application) 。要安装和使用生成器以及运行React应用程序服务器，需要安装[Node.js](https://nodejs.org/) JavaScript 运行时和 [npm](https://www.npmjs.com/) (Node.js 包管理器)。npm 包含在 Node.js 中，你可以从[此处](https://nodejs.org/en/download/)下载和安装。

>**Tip**: To test that you have Node.js and npm correctly installed on your machine, you can type `node --version` and `npm --version` in a terminal or command prompt.

>**Tip**: 要测试您的计算机上是否正确安装了 Node.js 和npm，可以在终端或命令提示符中键入 `node --version` 和 `npm --version`。

To install the `create-react-app` generator, in a terminal or command prompt type:

要在终端或命令提示符中安装 `create-react-app` 生成器，请键入：

```bash
npm install -g create-react-app
```

This may take a few minutes to install. You can now create a new React application by typing:

安装可能需要几分钟。现在可以通过键入以下内容创建新的React应用程序：

```bash
create-react-app my-app
```

where `my-app` is the name of the folder for your application. This may take a few minutes to create the React application and install its dependencies.

其中 `my-app` 是应用程序文件夹的名称。这可能需要几分钟来创建 React 应用程序并安装其依赖项。

Let's quickly run our React application by navigating to the new folder and typing `npm start` to start the web server and open the application in a browser:

让我们通过导航到新文件夹并键入 `npm start` 来启动Web服务器并在浏览器中打开应用程序，从而快速运行我们的 React 应用程序：

```bash
cd my-app
npm start
```

You should see "Welcome to React" on [http://localhost:3000](http://localhost:3000) in your browser. We'll leave the web server running while we look at the application with VS Code.

您应该在浏览器中的 [http://localhost:3000](http://localhost:3000) 上看到 "Welcome to React" 。我们将让Web服务器继续运行，同时用VS代码查看应用程序。

To open your React application in VS Code, open another terminal or command prompt window, navigate to the `my-app` folder and type `code .`:

要在vs代码中打开您的React应用程序，请打开另一个终端或命令提示窗口，导航到 `my-app` 文件夹并键入 `code .` 。

```bash
cd my-app
code .
```

### Markdown preview

In the File Explorer, one file you'll see is the application `README.md` Markdown file. This has lots of great information about the application and React in general. A nice way to review the README is by using the VS Code [Markdown Preview](/docs/languages/markdown.md#markdown-preview). You can open the preview in either the current editor group (**Markdown: Open Preview** `kb(markdown.showPreview)`) or in a new editor group to the side (**Markdown: Open Preview to the Side** `kb(markdown.showPreviewToSide)`). You'll get nice formatting, hyperlink navigation to headers, and syntax highlighting in code blocks.

在文件资源管理器中，您将看到一个文件，即应用程序 `README.md` Markdown 文件。这有很多关于应用程序和 React 的重要信息。查看 README 的一个好方法是使用 VS Code [Markdown Preview](/docs/languages/markdown.md#markdown-preview) 。你可以在当前编辑器组 (**Markdown: Open Preview** `kb(markdown.showPreview)`) 中打开预览，也可以在新编辑器组的一侧 (**Markdown: Open Preview to the Side** `kb(markdown.showPreviewToSide)`) 中打开预览。您将获得良好的格式设置、到标题的超链接导航以及代码块中的语法突出显示。

![README markdown preview](images/reactjs/markdown-preview.png)

### Syntax highlighting and bracket matching

Now expand the `src` folder and select the `index.js` file. You'll notice that VS Code has syntax highlighting for the various source code elements and, if you put the cursor on a parentheses, the matching bracket is also selected.

现在展开 `src` 文件夹并选择 `index.js` 文件。您会注意到， VS Code 有各种源代码元素的语法突出显示，如果您将光标放在圆括号上，那么匹配的括号也会被选中。

![react bracket matching](images/reactjs/bracket-matching.png)

### IntelliSense

As you start typing in `index.js`, you'll see smart suggestions or completions.

当你开始在 `index.js` 中输入时，你会看到一些明智的建议或补充。

![react suggestions](images/reactjs/suggestions.png)

After you select a suggestion and type `.`, you see the types and methods on the object through [IntelliSense](/docs/editor/intellisense.md).

选择建议和类型 `.` 后，通过[IntelliSense](/docs/editor/intellisense.md) 查看对象上的类型和方法。

![react intellisense](images/reactjs/intellisense.png)

VS Code uses the TypeScript language service for its JavaScript code intelligence and it has a feature called [Automatic Type Acquisition](/docs/languages/javascript.md#automatic-type-acquisition) (ATA). ATA pulls down the npm Type Declaration files (`*.d.ts`) for the npm modules referenced in the `package.json`.

VS Code 将 TypeScript 语言服务用于其 JavaScript 代码智能，并具有一个名为 [Automatic Type Acquisition](/docs/languages/javascript.md#automatic-type-acquisition) (ATA) 的功能。
ATA 会下拉 `package.json` 中引用的 npm 模块的类型声明文件(`*.d.ts`) 。

If you select a method, you'll also get parameter help:

如果选择一个方法，还将获得参数帮助：

![react parameter help](images/reactjs/parameter-help.png)

### Go to Definition, Peek definition

Through the TypeScript language service, VS Code can also provide type definition information in the editor through **Go to Definition** (`kb(editor.action.revealDefinition)`) or **Peek Definition** (`kb(editor.action.peekDefinition)`). Put the cursor over the `App`, right click and select **Peek Definition**. A [Peek window](/docs/editor/editingevolved.md#peek) will open showing the `App` definition from `App.js`.

通过 TypeScript 语言服务，vs code还可以通过 **转到定义** (`kb(editor.action.revealDefinition)`) 或 **查看定义** (`kb(editor.action.peekDefinition)`) 在编辑器中提供类型定义信息。将光标放在 `App` 上，右键单击并选择 **查看定义**。将打开一个 [Peek window](/docs/editor/editingevolved.md#peek) ，显示 `App.js` 中的 `App` 定义。

![react peek definition](images/reactjs/peek-definition.png)

Press `kbstyle(Escape)` to close the Peek window.

按 `kbstyle(Escape)` 关闭这个查看窗口。

## Hello World!

Let's update the sample application to "Hello World!". Add the link to declare a new H1 header and replace the `<App />` tag in `ReactDOM.render` with `element`.

让我们将示例应用程序更新为 "Hello World!" 。添加链接以声明新的 H1 头并将 `ReactDOM.render` 中的 `<App />` 标记替换为 `element` 。

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import registerServiceWorker from './registerServiceWorker';
import './index.css';

var element = React.createElement('h1', { className: 'greeting' }, 'Hello, world!');
ReactDOM.render(element, document.getElementById('root'));
registerServiceWorker();
```

Once you save the `index.js` file, the running instance of the server will update the web page and you'll see "Hello World!".

保存 `index.js` 文件后，正在运行的服务器实例将更新网页，您将看到 "Hello World!" 。

>**Tip**: VS Code supports Auto Save, which by default saves your files after a delay. Check the **Auto Save** option in the **File** menu to turn on Auto Save or directly configure the `files.autoSave` user [setting](/docs/getstarted/settings.md).

>**Tip**: VS Code 支持自动保存，默认情况下，自动保存会在延迟后保存文件。选中 **文件** 菜单中的 **自动保存** 选项，打开自动保存或直接配置 `files.autoSave` 用户[设置](/docs/getstarted/settings.md) 。

![hello world](images/reactjs/hello-world.png)

## Debugging React

To debug the client side React code, we'll need to install the [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) extension.

要调试客户端 React 代码，我们需要安装 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 插件。

>Note: This tutorial assumes you have the Chrome browser installed. Microsoft also publishes a version of this extension for their [Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) browser.

>Note: 本教程假设您安装了Chrome浏览器。 Microsoft 还为其 Edge 浏览器发布了[Edge插件](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) 。

Open the Extensions view (`kb(workbench.view.extensions)`) and type `chrome` in the search box. You'll see several extensions which reference Chrome.

打开插件视图 (`kb(workbench.view.extensions)`) ，在搜索框中键入 `chrome` 。您将看到几个引用 Chrome 的插件。

![debugger for chrome](images/reactjs/debugger-for-chrome.png)

Press the **Install** button for **Debugger for Chrome**.

点击  **Debugger for Chrome** 的 **Install** 按钮。

### Set a breakpoint

To set a breakpoint in `index.js`, click on the gutter to the left of the line numbers. This will set a breakpoint which will be visible as a red circle.

要在 `index.js`中设置断点，请单击行号左侧的装订线。这将设置一个断点，该断点将显示为一个红色圆圈。

![set a breakpoint](images/reactjs/breakpoint.png)

### Configure the Chrome debugger

We need to initially configure the [debugger](/docs/editor/debugging.md). To do so, go to the Debug view (`kb(workbench.view.debug)`) and click on the gear button to create a `launch.json` debugger configuration file. Choose **Chrome** from the **Select Environment** drop-down list. This will create a `launch.json` file in a new `.vscode` folder in your project which includes a configuration to launch the website.

我们需要首先配置 [debugger](/docs/editor/debugging.md) 。要执行此操作，请转到“调试”视图 (`kb(workbench.view.debug)`) ，然后单击齿轮按钮以创建 `launch.json` 调试程序配置文件。从 **Select Environment** 下拉列表中选择 **Chrome** 。这将在项目中的新的 `.vscode` 文件夹中创建一个 `launch.json` 文件，其中包括启动网站的配置。

We need to make one change for our example: change the port of the `url` from `8080` to `3000`. Your `launch.json` should look like this:

我们需要对示例进行一次更改：将 `url` 的端口从 `8080` 更改为 `3000`。你的 `launch.json` 应该如下所示：

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "chrome",
            "request": "launch",
            "name": "Launch Chrome against localhost",
            "url": "http://localhost:3000",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```

Ensure that your development server is running ("npm start"). Then press `kb(workbench.action.debug.start)` or the green arrow to launch the debugger and open a new browser instance. The source code where the breakpoint is set runs on startup before the debugger was attached so we won't hit the breakpoint until we refresh the web page. Refresh the page and you should hit your breakpoint.

确保你的开发服务器正在运行 ("npm start") 。然后按 `kb(workbench.action.debug.start)` 或绿色箭头启动调试器并打开新的浏览器实例。在附加调试器之前，设置断点的源代码在启动时运行，因此在刷新网页之前，我们不会命中断点。刷新页面，应该可以命中断点。

![hit breakpoint](images/reactjs/hit-breakpoint.png)

You can step through your source code (`kb(workbench.action.debug.stepOver)`), inspect variables such as `element`, and see the call stack of the client side React application.

您可以单步执行源代码 (`kb(workbench.action.debug.stepOver)`) ，检查变量（如 `element`），并查看客户端 React 应用程序的调用堆栈。

![debug variable](images/reactjs/debug-variable.png)

The **Debugger for Chrome** extension README has lots of information on other configurations, working with sourcemaps, and troubleshooting. You can review it directly within VS Code from the **Extensions** view by clicking on the extension item and opening the **Details** view.

针对**Debugger for Chrome** 插件 README 包含许多关于其他配置、使用源映射和故障排除的信息。通过单击扩展项并打开**详细信息**视图，您可以直接在VS代码中从**扩展**视图中查看它。

![debugger for chrome readme](images/reactjs/chrome-debugger-readme.png)

### Live editing and debugging 实时编辑和调试

If you are using [webpack](https://webpack.js.org/) together with your React app, you can have a more efficient workflow by taking advantage of webpack's HMR mechanism which enables you to have live editing and debugging directly from VS Code. You can learn more in this [Live edit and debug your React apps directly from VS Code](https://medium.com/@auchenberg/live-edit-and-debug-your-react-apps-directly-from-vs-code-without-leaving-the-editor-3da489ed905f) blog post.

如果你将 [webpack](https://webpack.js.org/) 与你的 React 应用程序一起使用，你可以利用 webpack 的 HMR 机制来实现更高效的工作流，该机制允许你直接从 VS Code 进行实时编辑和调试。你可以在 [Live edit and debug your React apps directly from VS Code](https://medium.com/@auchenberg/live-edit-and-debug-your-react-apps-directly-from-vs-code-without-leaving-the-editor-3da489ed905f) 中了解更多信息。

## Linting

Linters analyze your source code and can warn you about potential problems before you run your application. The JavaScript language services included with VS Code has syntax error checking support by default which you can see in action in the **Problems** panel (**View** > **Problems** `kb(workbench.actions.view.problems)`).

Linters 可以分析源代码，并在运行应用程序之前警告您潜在的问题。与 VS Code 一起提供的 JavaScript 语言服务在默认情况下具有语法错误检查支持，你可以在**Problems**面板 (**View** > **Problems** `kb(workbench.actions.view.problems)` )中看到它的实际应用。

Try making a small error in your React source code and you'll see a red squiggle and an error in the **Problems** panel.

尝试在你的 React 源代码中犯一个小错误，您将在**问题**面板中看到一个红色的曲线和一个错误。

![javascript error](images/reactjs/js-error.png)

Linters can provide more sophisticated analysis, enforcing coding conventions and detecting anti-patterns. A popular JavaScript linter is [ESLint](https://eslint.org/). ESLint, when combined with the ESLint VS Code [extension](https://marketplace.visualstudio.com/items/dbaeumer.vscode-eslint), provides a great in-product linting experience.

Linters可以提供更复杂的分析、强制编码约定和检测反模式。一个流行的JavaScript linter是 [ESLint](https://eslint.org/) 。ESLint 与ESLint VS Code [extension](https://marketplace.visualstudio.com/items/dbaeumer.vscode-eslint) 结合使用时，提供了非常好的产品连接性体验。

First, install the ESLint command line tool:

首先，安装 ESLint 命令行工具：

```bash
npm install -g eslint
```

Then install the ESLint extension by going to the **Extensions** view and typing 'eslint'.

然后转到**插件**视图并键入 'eslint' ，安装 ESLint 插件。

![ESLint extension](images/reactjs/eslint-extension.png)

Once the ESLint extension is installed and VS Code reloaded, you'll want to create an ESLint configuration file `.eslintrc.json`. You can create one using the extension's **ESLint: Create ESLint configuration** command from the **Command Palette** (`kb(workbench.action.showCommands)`).

一旦安装了 ESLint 插件并重新加载了 VS Code ，你就需要创建一个 ESLint 配置文件 `.eslintrc.json` 。您可以在 **Command Palette** (`kb(workbench.action.showCommands)`) 使用插件的 **ESLint: Create ESLint configuration** 命令来创建一个。

![create eslintrc](images/reactjs/create-eslintrc.png)

The command will create a `.eslintrc.json` file in your project root:

该命令将在项目根目录中创建一个 `.eslintrc.json` 文件：

```json
{
    "env": {
        "browser": true,
        "commonjs": true,
        "es6": true,
        "node": true
    },
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "sourceType": "module"
    },
    "rules": {
        "no-const-assign": "warn",
        "no-this-before-super": "warn",
        "no-undef": "warn",
        "no-unreachable": "warn",
        "no-unused-vars": "warn",
        "constructor-super": "warn",
        "valid-typeof": "warn"
    }
}
```

ESLint will now analyze open files and shows a warning in `index.js` about 'App' being defined but never used.

ESLint 现在将分析打开的文件，并在 `index.js` 中显示一条关于 'App' 正在定义但从未使用的警告。

![App is unused](images/reactjs/app-is-unused.png)

You can modify the ESLint [rules](https://eslint.org/docs/rules/) and the ESLint extension provides IntelliSense in `.eslintrc.json`.

您可以修改ESLint [rules](https://eslint.org/docs/rules/) 并且 ESLint 插件在 `.eslintrc.json` 中提供智能提示。

![eslintrc IntelliSense](images/reactjs/eslintrc-intellisense.png)

Let's add an error rule for extra semi-colons:

让我们为额外的分号添加一个错误规则：

```json
 "rules": {
        "no-const-assign": "warn",
        "no-this-before-super": "warn",
        "no-undef": "warn",
        "no-unreachable": "warn",
        "no-unused-vars": "warn",
        "constructor-super": "warn",
        "valid-typeof": "warn",
        "no-extra-semi":"error"
    }
```

Now when you mistakenly have multiple semicolons on a line, you'll see an error (red squiggle) in the editor and error entry in the **Problems** panel.

现在，当你在一行中错误地使用多个分号时，你将在编辑器中看到一个错误（红色波形），并在**问题**面板中看到错误条目。

![extra semicolon error](images/reactjs/extra-semi-error.png)

## Popular Starter Kits

In this tutorial, we used the `create-react-app` generator to create a simple React application. There are lots of great samples and starter kits available to help build your first React application.

在本教程中，我们使用 `create-react-app` 生成器创建一个简单的 React 应用程序。有很多很好的示例和入门工具包可以帮助构建您的第一个React应用程序。

### VS Code React Sample

This is a [sample](https://github.com/Microsoft/vscode-react-sample) React application used for a [demo](https://channel9.msdn.com/events/Build/2017/T6078) at this year's //Build conference. The sample creates a simple TODO application and includes the source code for a Node.js [Express](https://expressjs.com/) server. It also shows how to use the [Babel](https://babeljs.io) ES6 transpiler and then use [webpack](https://webpack.js.org/) to bundle the site assets.

这是一个 React 应用程序[示例](https://github.com/Microsoft/vscode-react-sample)，用于今年的 //Build 会议上的[演示](https://channel9.msdn.com/events/Build/2017/T6078) 。该示例创建一个简单的 TODO 应用程序，并包含 Node.js [Express](https://expressjs.com/) 服务器的源代码。它还展示了如何使用[Babel](https://babeljs.io) ES6 transpiler ，然后使用[webpack](https://webpack.js.org/) 编译站点资产。

### MERN Starter

If you'd like to see a full MERN (MongoDB, Express, React, Node.js) stack example, look at the [MERN Starter](http://mern.io/). You'll need to install and start [MongoDB](https://docs.mongodb.com/v3.0/installation/) but you'll quickly have a MERN application running. There is helpful VS Code-specific documentation at [vscode-recipes](https://github.com/Microsoft/vscode-recipes/tree/master/MERN-Starter) which details setting up Node.js server debugging. VS Code also has great [MongoDB support](/docs/azure/mongodb.md) through the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension.

如果你希望看到完整的 MERN (MongoDB, Express, React, Node.js) 堆栈示例，请查看[MERN Starter](http://mern.io/) 。你需要安装并启动 [MongoDB](https://docs.mongodb.com/v3.0/installation/) ，但是你很快就会有一个 MERN 应用程序。在[[vscode-recipes](https://github.com/Microsoft/vscode-recipes/tree/master/MERN-Starter) 上有一些有用的 VS Code-specific  文档，这些文档详细介绍了如何设置 Node.js 服务器调试。 VS Code 还通过[Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) 提供了出色的 [MongoDB support](/docs/azure/mongodb.md) 。

### TypeScript React

If you're curious about TypeScript and React, you can also create a TypeScript version of the `create-react-app` application. See the details at [TypeScript-React-Starter](https://github.com/Microsoft/TypeScript-React-Starter) on the [TypeScript Quick Start](https://www.typescriptlang.org/samples/index.html) site.

如果您对 TypeScript 和 React 感兴趣，还可以创建 `create-react-app` 应用程序的 TypeScript 版本。有关详细信息，请访问 [TypeScript-React-Starter](https://github.com/Microsoft/TypeScript-React-Starter) ，网址为 [TypeScript Quick Start](https://www.typescriptlang.org/samples/index.html) 。

### Angular

[Angular](https://angular.io/) is another popular web framework. If you'd like to see an example of Angular working with VS Code, check out the [Chrome Debugging with Angular CLI](https://github.com/Microsoft/vscode-recipes/tree/master/Angular-CLI) recipe. It will walk you through creating an Angular application and configuring the `launch.json` file for the [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) extension.

[Angular](https://angular.io/) 是另一个流行的Web框架。如果你希望看到一个使用 VS Code 的 Angular 工作示例，请查看 [Chrome Debugging with Angular CLI](https://github.com/Microsoft/vscode-recipes/tree/master/Angular-CLI) 。它将引导你创建一个 Angular 应用程序，并为 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 配置 `launch.json` 文件。

## Common questions

### Can I get IntelliSense within declarative JSX? 我可以在声明性JSX中获得智能提示吗？

Yes. For example, if you open the `create-react-app` project's `App.js` file, you can see IntelliSense within the React JSX in the `render()` method.

可以。例如，如果打开 `create-react-app` 项目的 `App.js` 文件，则可以在 `render()` 方法中的 React JSX 中看到智能提示。

![JSX IntelliSense](images/reactjs/jsx-intellisense.png)
