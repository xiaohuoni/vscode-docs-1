---
Order: 4
Area: typescript
TOCTitle: Debugging
ContentId: 19c60eb6-662b-444a-92f6-009642cc1e5b
PageTitle: TypeScript debugging with Visual Studio Code
DateApproved: 3/7/2019
MetaDescription: TypeScript debugging with Visual Studio Code.
MetaSocialImage: images/typescript-tutorial/Languages_typescript.png
---
# Debugging TypeScript 调试 TypeScript

Visual Studio Code supports TypeScript debugging through its built-in [Node.js debugger](/docs/nodejs/nodejs-debugging.md) and also through [extensions](/docs/editor/extension-gallery.md) like [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) to support client-side TypeScript debugging.

Visual Studio Code 支持通过其内置的 [Node.js调试器](/docs/nodejs/nodejs-debugging.md) 进行 TypeScript 调试，也支持通过诸如 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 之类的[插件](/docs/editor/extension-gallery.md)来支持客户端 TypeScript 调试。

## JavaScript source map support  JavaScript 源映射支持

TypeScript debugging supports JavaScript source maps. To generate source maps for your TypeScript files, compile with the `--sourcemap` option or set the `sourceMap` property in the `tsconfig.json` file to `true`.

TypeScript 调试支持 JavaScript 源映射。要为 TypeScript 文件生成源映射，请使用 `--sourceMap` 选项进行编译或将 `tsconfig.json` 文件中的 `sourceMap` 属性设置为 `true`。

In-lined source maps (a source map where the content is stored as a data URL instead of a separate file) are also supported, although in-lined source is not yet supported.

也支持内联源映射(其中内容存储为数据URL而不是单独文件的源映射)，尽管目前还不支持内联源。

For a simple example of source maps in action, see the [TypeScript tutorial](/docs/typescript/typescript-tutorial.md), which shows debugging a simple "Hello World" Node.js application using the following `tsconfig.json` and VS Code default Node.js debugging configuration.

有关实际中的源映射的简单示例，请参阅 [TypeScript 教程](/docs/typescript/typescript-tutorial.md)，该教程显示使用以下 `tsconfig.json` 和 VS Code 默认 Node.js 调试配置调试简单的 "Hello World" Node.js 应用程序。

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "outDir": "out",
        "sourceMap": true
    }
}
```

For more advanced debugging scenarios, you can create your own debug configuration `launch.json` file. To see the default configuration, go to the Debug view (`kb(workbench.view.debug)`) and press the gear icon to **Configure or Fix 'launch.json'**. If you have other debugger extensions installed (such as the Debugger for Chrome), you should select **Node.js** from the drop down.

对于更高级的调试方案，可以创建自己的调试配置 `launch.json` 文件。要查看默认配置，请转到调试视图 (`kb(workbench.view.debug)`) ，然后按齿轮图标**配置或修复 'launch.json' ** 。如果安装了其他调试器插件(如用于 Debugger for Chrome )，则应从下拉列表中选择 **Node.js**。

![configure launch.json](images/debugging/configure-debugging.png)

This will create a `launch.json` file in a `.vscode` folder with default values detected in your project.

这将在 `.vscode` 文件夹中创建 `launch.json` 文件，并在项目中检测到默认值。

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "${workspaceFolder}/helloworld.ts",
            "preLaunchTask": "tsc: build - tsconfig.json",
            "outFiles": [
                "${workspaceFolder}/out/**/*.js"
            ]
        }
    ]
}
```

VS Code has determined the program to launch, `helloworld.ts`, included the build as a `preLaunchTask`, and told the debugger where to find the generated JavaScript files.

VS Code 已经确定了要启动的 `helloworld.ts` 程序，包括构建一个 `预启动任务` ，并告诉调试器在哪里可以找到生成的 JavaScript 文件。

There is full IntelliSense with suggestions and information for `launch.json` to help you learn about other debug configuration options. You can also add new debug configurations to `launch.json` with the **Add Configuration** button in the lower right.

有完整的智能提示，其中包含 `launch.json` 的建议和信息，以帮助了解其他调试配置选项。还可以使用右下角的**添加配置**按钮向 `launch.json` 添加新的调试配置。

![launch.json IntelliSense](images/debugging/launch-json-intellisense.png)

Also see [Node.js Debugging](/docs/nodejs/nodejs-debugging.md) for examples and further explanations.

有关示例和进一步说明，请参见 [Node.js 调试](/docs/nodejs/nodejs-debugging.md)。

## Mapping the output location 映射输出位置

If generated (transpiled) JavaScript files do not live next to their source, you can help the VS Code debugger locate them by setting the `outFiles` attribute in the launch configuration. Whenever you set a breakpoint in the original source, VS Code tries to find the generated source by searching the files specified by glob patterns in `outFiles`.

如果生成的(发出来的) JavaScript 文件不在它们的源代码旁边，可以通过在启动配置中设置 `outFiles` 属性来帮助 VS Code 调试器定位它们。每当在原始源中设置断点时，VS Code 都会通过搜索由 `outFiles` 中的 glob 模式指定的文件来尝试查找生成的源。

## Client-side debugging  客户端调试

TypeScript is great for writing client-side code as well as Node.js applications and you can debug client-side source code with extensions such as [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome).

TypeScript 非常适合于编写客户端代码以及 Node.js 应用程序，可以使用诸如 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 之类的插件来调试客户端源代码。

We'll create a tiny web application to show client-side debugging in action.

我们将创建一个小的Web应用程序来显示客户端调试的实际效果。

Create a new folder `HelloWeb` and add three files: `helloweb.ts`, `helloweb.html`, and `tsconfig.json` with the following content"

创建一个新文件夹 `HelloWeb` 并添加三个文件： `helloweb.ts` ，`helloweb.html` 和 `tsconfig.json` ，内容如下

helloweb.ts

```typescript
let message : string = "Hello Web";
document.body.innerHTML = message;
```

helloweb.html

```html
<!DOCTYPE html>
<html>
    <head><title>TypeScript Hello Web</title></head>
    <body>
        <script src="out/helloweb.js"></script>
    </body>
</html>
```

tsconfig.json

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "outDir": "out",
        "sourceMap": true
    }
}
```

Run `tsc` to build the app and then test by opening `helloweb.html` in your browser (you can right click `helloweb.html` in the File Explorer and select **Copy Path** to paste into your browser).

运行 `tsc` 构建应用程序，然后通过在浏览器中打开 `helloweb.html` 进行测试(可以在文件资源管理器中右键单击 `helloweb.html` ，然后选择**复制**路径粘贴到浏览器中)。

To debug the client-side code, install the [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) [extension](/docs/editor/extension-gallery.md). Open the Extensions view (`kb(workbench.view.extensions)`) and search for "Chrome". Install the extension and reload VS Code.

要调试客户端代码，请安装用于 [插件](/docs/editor/extension-gallery.md) 的 [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 。打开插件视图 (`kb(workbench.view.extensions)`) 并搜索 "Chrome" 。安装插件并重新加载 VS Code 。

![debugger for chrome extension](images/debugging/debugger-for-chrome.png)

In the Debug view, press the gear icon to create a `launch.json` file selecting **Chrome** as the debugger.

在 Debug 视图中，Gear 点击齿轮标志按钮创建一个 `launch.json` 文件，选择 **chrome** 作为调试器。

Update the `launch.json` to specify the local file URL to `helloweb.html`:

更新 `launch.json` 以指定 `helloweb.html` 的本地文件URL:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "chrome",
            "request": "launch",
            "name": "Launch Chrome against localhost",
            "url": "file:///C:/Users/gregvanl/deleteMe/HelloWeb/helloweb.html",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```

The Debug view configuration dropdown will now show the new configuration **Launch Chrome against localhost**. If you run that configuration, your browser will launch with your web page. Open `helloweb.ts` in the editor and click the left gutter to add a breakpoint (it will be displayed as a red circle). Press `kb(workbench.action.debug.start)` to start the debug session, which launches the browser and hits your breakpoint in `helloweb.ts`.

调试视图配置下拉列表现在将显示新的配置针对**本地主机启动chrome** 。如果运行该配置，浏览器将随网页一起启动。在编辑器中打开 `helloweb.ts` ，单击左边的装订线添加一个断点(它将显示为一个红色圆圈)。按 `kb(workbench.action.debug.start)` 启动调试会话，该会话将启动浏览器并在 `helloweb.ts` 中命中断点。

![client-side debug breakpoint](images/debugging/client-side-debug-breakpoint.png)

## Common questions 常见问题

### Cannot launch program because corresponding JavaScript cannot be found 无法启动程序，因为找不到相应的 JavaScript

You've likely not set `"sourceMap": true` in your `tsconfig.json` or `outFiles` in your `launch.json` and the VS Code Node.js debugger can't map your  source code to the running JavaScript. Turn on source maps and rebuild your project.

您可能没有设置 `"sourceMap": true` 在 `tsconfig.json` 中，或者在 `launch.json` 中为 `outFiles` ，而 VS Code Node.js 调试器无法将您的 TypeScript 源代码映射到正在运行的 JavaScript 。打开源映射并重建项目。
