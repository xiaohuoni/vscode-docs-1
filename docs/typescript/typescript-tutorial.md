---
Order: 1
Area: typescript
TOCTitle: Tutorial
ContentId: cb4f3742-733c-49d8-96db-d4bf8403bf64
PageTitle: TypeScript tutorial with Visual Studio Code
DateApproved: 3/7/2019
MetaDescription: TypeScript tutorial with Visual Studio Code.
MetaSocialImage: images/typescript-tutorial/Languages_typescript.png
---
# TypeScript tutorial in Visual Studio Code Visual Studio Code中的TypeScript教程


[ TypeScript ](https://www.typescriptlang.org) is a typed superset of JavaScript that compiles to plain JavaScript. It offers classes, modules, and interfaces to help you build robust components. The TypeScript language specification can be found [here](https://github.com/Microsoft/TypeScript/tree/master/doc).

[ TypeScript ](https://www.typescriptlang.org)是一个类型化的 JavaScript 超集，编译为纯 JavaScript 。它提供类、模块和接口来帮助您构建健壮的组件。可以在此处找到 TypeScript 语言规范[here](https://github.com/Microsoft/TypeScript/tree/master/doc)。

## Install the TypeScript compiler 安装 TypeScript 编辑器

Visual Studio Code includes TypeScript language support but does not include the TypeScript compiler, `tsc`. You will need to install the TypeScript compiler either globally or in your workspace to transpile TypeScript source code to JavaScript (`tsc HelloWorld.ts`).

Visual Studio Code包括对 TypeScript 语言的支持，但不包括 TypeScript 编译器,`tsc`。您需要在全局或工作区中安装 TypeScript 编译器，以便将 TypeScript 源代码生成到 JavaScript (`tsc HelloWorld.ts`)。

The easiest way to install TypeScript is through npm, the [Node.js Package Manager](https://www.npmjs.com/). If you have npm installed, you can install TypeScript globally (`-g`) on your computer by:

安装 TypeScript 最简单的方法是通过npm，[node.js包管理器](https://www.npmjs.com/)。如果安装了NPM，则可以通过以下方式在计算机上全局(`-g`)安装 TypeScript ：

```bash
npm install -g typescript
```

You can test your install by checking the version.

您可以通过检查版本来测试安装。

```bash
tsc --version
```

## Hello World

Let's start with a simple Hello World Node.js example. Create a new folder `HelloWorld` and launch VS Code.

让我们从一个简单的hello world node.js示例开始。创建新文件夹`HelloWorld`并启动vs Code。

```
mkdir HelloWorld
cd HelloWorld
code .
```

From the File Explorer, create a new file called `helloworld.ts`.

从文件资源管理器中，创建一个名为`helloworld.ts`的新文件。

![create new file](images/tutorial/create-new-file.png)

Now add the following TypeScript code. You'll notice the TypeScript keyword `let` and the `string` type declaration.

现在添加以下 TypeScript code。您会注意到 TypeScript 关键字`let` 和字符串`string`类型声明


```typescript
let message : string = "Hello World";
console.log(message);
```

To compile your TypeScript code, you can open the [Integrated Terminal](/docs/editor/integrated-terminal.md) (`kb(workbench.action.terminal.toggleTerminal)`) and typing `tsc helloworld.ts`. This will compile and create a new `HelloWorld.js` JavaScript file.

要编译 TypeScript 代码，可以打开集成终端(`kb(workbench.action.terminal.toggleTerminal)`)，然后键入`tsc helloworld.ts`。这将编译并创建一个新的helloworld.js JavaScript 文件。

![compiled hello world](images/tutorial/compiled-hello-world.png)

If you have Node.js installed, you can run `node helloworld.js`.

如果安装了node.js，则可以运行`node helloworld.js`。

![run hello world](images/tutorial/run-hello-world.png)

If you open `helloworld.js`, you'll see that it doesn't look very different from `helloworld.ts`. The type information has been removed and `let` is now `var`.

如果你打开`helloworld.js`，你会发现它看起来和`helloworld.ts`没有什么不同。类型信息已被删除，现在`let`为`var`。

```javascript
var message = "Hello World";
console.log(message);
```

## IntelliSense 智能提示

In the VS Code, you can see that you get language features such as syntax highlighting and bracket matching. When you were typing in the editor, you may have noticed IntelliSense, the smart code completions and suggestion provided by VS Code and the TypeScript language server. Below you can see the methods of `console`

在vs Code中，您可以看到您获得了语言特性，如语法突出显示和括号匹配。在编辑器中键入时，您可能注意到智能提示、VS Code和 TypeScript 语言服务器提供的智能代码完成和建议。下面您可以看到`console`的方法

![IntelliSense](images/tutorial/intellisense.png)

When you select a method, you then get parameter help and can always get hover information.

当您选择一个方法时，您将获得参数帮助，并且可以始终获得悬停信息。

![parameter help](images/tutorial/parameter-help.png)

## tsconfig.json

So far in this tutorial, you have been relying on the TypeScript compiler's default behavior to compile your TypeScript source code. You can modify the TypeScript compiler options by adding a `tsconfig.json` file which defines the TypeScript [project settings](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) such as the [compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html) and the files that should be included.

到目前为止，在本教程中，您一直依赖于 TypeScript 编译器的默认行为来编译您的 TypeScript 源代码。您可以通过添加`tsconfig.json`文件来修改 TypeScript 编译器选项，该文件定义了 TypeScript [项目设置](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) ，如[编译器选项](https://www.typescriptlang.org/docs/handbook/compiler-options.html)和应包含的文件。

Add a simple `tsconfig.json` which set the options to compile to ES5 and use **CommonJS** [modules](http://www.commonjs.org/specs/modules/1.0).

添加一个简单的`tsconfig.json`，其中设置了编译ES5和使用**CommonJS**[模块](http://www.commonjs.org/specs/modules/1.0)的选项。

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs"
    }
}
```

When editing `tsconfig.json`, IntelliSense (`kb(editor.action.triggerSuggest)`) will help you along the way.

当编辑`tsconfig.json`，IntelliSense(`kb(editor.action.triggerSuggest)`)将一直帮助你。

![tsconfig.json IntelliSense](images/tutorial/tsconfig-intellisense.png)

By default, TypeScript includes all the `.ts` files in the current folder and subfolders if the `files` attribute isn't included so we don't need to list `helloworld.ts` explicitly.

默认情况下，如果不包含`files` 属性，TypeScript 将包含当前文件夹和子文件夹中的所有`.ts`文件，因此不需要显式列出 `helloworld.ts` 。

Now to build from the terminal, you can just type `tsc` and the TypeScript compiler knows to look at your `tsconfig.json` for project settings and compiler options.

现在，要从终端构建，只需键入`tsc`，TypeScript 编译器就知道要查看`tsconfig.json`中的项目设置和编译器选项。

### Change the build output 更改生成的输出

Having the generated JavaScript file in the same folder at the TypeScript source will quickly get cluttered on larger projects, so you can specify the output directory for the compiler with the `outDir` attribute.

将生成的 JavaScript 文件放在 TypeScript 源的同一个文件夹中会很快在较大的项目中变得混乱，因此可以使用`outDir`属性为编译器指定输出目录。

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "outDir": "out"
    }
}
```

Delete `helloworld.js`, run `tsc` again and `helloworld.js` will be placed in an `out` directory.

删除`helloworld.js`，再次运行`tsc`，`helloworld.js`将被放在`out`目录中。

See [Compiling TypeScript](/docs/typescript/typescript-compiling.md) to learn about other features of the TypeScript language service and how to use tasks to run your builds directly from VS Code.

请参阅[编译 TypeScript ](/docs/typescript/typescript-compiling.md)以了解 TypeScript 语言服务的其他功能以及如何使用任务直接从vs Code运行生成。

## Error checking 错误检查

TypeScript helps you avoid common programming mistakes through strong type checking. For example, if you assign a number to `message`, the TypeScript compiler will complain with **'error TS2322: Type '2' is not assignable to type 'string'**.  You can see type checking errors in VS Code both the editor (red squillies with hover information) and the Problems panel (`kb(workbench.actions.view.problems)`). The `[ts]` prefix lets you know this error is coming from the TypeScript language service.

TypeScript 通过强类型检查帮助您避免常见的编程错误。例如，如果为 `message`分配一个数字，则 TypeScript 编译器将输出 **'error TS2322: Type '2' is not assignable to type 'string'**。您可以在VS代码中看到类型检查错误，包括编辑器（带有悬停信息的红色斜线）和问题面板(`kb(workbench.actions.view.problems)`)。`[ts]`前缀让您知道这个错误来自于 TypeScript 语言服务。

![incorrect type error](images/tutorial/incorrect-type-error.png)

## Quick Fixes 快速修复

The TypeScript language service has a powerful set of diagnostics to find common coding issues. For example it can analyze your source code and detect unreachable code which are displayed as dimmed in the editor. If you hover over the line of source code, you'll see a hover explaining and if you place your cursor on the line, you'll get a Quick Fix lightbulb.

TypeScript 语言服务具有一套强大的诊断功能，可以发现常见的编码问题。例如，它可以分析源代码并检测不可访问的代码，这些代码在编辑器中显示为灰色。如果您将鼠标悬停在源代码行上，您将看到一个悬停解释，如果您将光标放在行上，您将得到一个快速修复的灯泡。

![unreachable code detected](images/tutorial/unreachable-code-detected.png)

Clicking on the lightbulb or pressing `kb(editor.action.quickFix)` brings up the Quick Fix menu where you can select the **Remove unreachable code** fix.

单击灯泡或按 `kb(editor.action.quickFix)` 会弹出“快速修复”菜单，从中可以选择**Remove unreachable code**。

## Debugging 调试

VS Code has built-in support for TypeScript debugging. To support debugging TypeScript in combination with the executing JavaScript code, VS Code relies on [source maps](https://developer.mozilla.org/docs/Tools/Debugger/How_to/Use_a_source_map) for the debugger to map between the original TypeScript source code and the running JavaScript. You can create source maps during the build by setting `"sourceMap": true` in your `tsconfig.json`.

VS Code内置了对 TypeScript 调试的支持。为了支持结合正在执行的 JavaScript 代码调试 TypeScript，vs代码依赖于[源代码映射](https://developer.mozilla.org/docs/Tools/Debugger/How_to/Use_a_source_map)，以便调试器在原始 TypeScript 源代码和正在运行的 JavaScript 之间进行映射。通过在`tsconfig.json`中设置`"sourceMap": true`，可以在构建期间创建源映射。

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

Rebuild by running `tsc` and you should now have a `helloworld.js.map` in the `out` directory next to `helloworld.js`.

通过运行`tsc`重新生成，现在应该在 `helloworld.js`旁边的`out`目录中有一个`helloworld.js.map`。

With `helloworld.ts` open in the editor, press `kb(workbench.action.debug.start)`. If you have other debugger extensions installed (such as the Chrome Debug extension), you need to select **Node.js** from the dropdown.

在编辑器中打开`helloworld.ts`后，按`kb(workbench.action.debug.start)`。安装了gger扩展（例如chrome调试扩展），您需要从下拉列表中选择**Node.js**。

The debugger will start a session, run your code, and display the "Hello World" message in the Debug console panel.

调试程序将启动一个会话，运行代码，并在调试控制台面板中显示“hello world”消息。

![debug console output](images/tutorial/debug-console.png)

In `helloworld.ts`, set a breakpoint by clicking on the left gutter of the editor. You will see a red circle if the breakpoint is set. Press `kb(workbench.action.debug.start)` again. Execution will stop when the breakpoint is hit and you'll be able to see debugging information such as variable values and the call stack in the Debug view (`kb(workbench.view.debug)`).

在 `helloworld.ts`中，通过单击编辑器的左槽来设置断点。如果设置了断点，您将看到一个红色圆圈。再次按`kb(workbench.action.debug.start)`。当断点被点击时，执行将停止，您将能够在调试视图 (`kb(workbench.view.debug)`)中看到调试信息，如变量值和调用堆栈。

![debug breakpoint](images/tutorial/debug-breakpoint.png)

See [Debugging TypeScript ](/docs/typescript/typescript-debugging.md) to learn more about VS Code's built-in debugging support for TypeScript and how you can configure the debugger for your project scenarios.

请参阅调试[ TypeScript ](/docs/typescript/typescript-debugging.md) 以了解有关vs code对 TypeScript 的内置调试支持以及如何为项目方案配置调试器的更多信息。

## Next steps 下一步

This tutorial was a quick introduction to using VS Code for TypeScript development. Read on to learn more about using VS Code's compiling and debugging support for TypeScript:

本教程简要介绍了如何使用vs Code进行 TypeScript 开发。继续阅读了解有关使用vs code对 TypeScript 的编译和调试支持的更多信息：

* [Compiling TypeScript](/docs/typescript/typescript-compiling.md) - Use VS Code's powerful task system for compiling TypeScript.
* [Debugging TypeScript](/docs/typescript/typescript-debugging.md) - Configure the debugger for your TypeScript project.

* [编译 TypeScript ](/docs/typescript/typescript-compiling.md)-使用vs code强大的任务系统来编译 TypeScript 。
* [调试 TypeScript ](/docs/typescript/typescript-debugging.md)-为 TypeScript 项目配置调试器。

## Common questions 常见问题

### Cannot launch program because corresponding JavaScript cannot be found 无法启动程序，因为找不到相应的 JavaScript 

You've likely not set `"sourceMap": true` in your `tsconfig.json` and the VS Code Node.js debugger can't map your TypeScript source code to the running JavaScript. Turn on source maps and rebuild your project.

您可能没有在 `tsconfig.json` 中设置 `"sourceMap": true`，而vs code node.js调试器无法将您的 TypeScript 源代码映射到正在运行的 JavaScript 。打开源映射并重建项目。
