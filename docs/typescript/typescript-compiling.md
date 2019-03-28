---
Order: 3
Area: typescript
TOCTitle: Compiling
ContentId: 59543856-da91-4a0d-9a98-9d5f2bf70c71
PageTitle: TypeScript Compiling with Visual Studio Code
DateApproved: 3/7/2019
MetaDescription: Learn about TypeScript compiling with Visual Studio Code.
---
# Compiling TypeScript 编译 TypeScript

[TypeScript](https://www.typescriptlang.org) is a typed superset of JavaScript that compiles to plain JavaScript. It offers classes, modules, and interfaces to help you build robust components. The TypeScript language specification can be found [here](https://github.com/Microsoft/TypeScript/tree/master/doc).

[TypeScript](https://www.typescriptlang.org) 是一个类型化的 JavaScript 超集，编译为纯 JavaScript 它提供类、模块和接口来帮助您构建健壮的组件。它提供类、模块和接口来帮助您构建健壮的组件。可以在[这里](https://github.com/Microsoft/TypeScript/tree/master/doc)找到 TypeScript 语言规范。

## Install the TypeScript compiler 安装 TypeScript 编译器

Visual Studio Code includes TypeScript language support but does not include the TypeScript compiler, `tsc`. You will need to install the TypeScript compiler either globally or in your workspace to transpile TypeScript source code to JavaScript (`tsc HelloWorld.ts`).

Visual Studio Code 支持 TypeScript 语言，但不包括 TypeScript 编译器，`tsc`。你需要在全局或者你的工作空间里安装 TypeScript 编译器，以将 TypeScript 源代码生成到 JavaScript (`tsc HelloWorld.ts`)。

The easiest way to install TypeScript is through npm, the [Node.js Package Manager](https://www.npmjs.com/). If you have npm installed, you can install TypeScript globally (`-g`) on your computer by:

最简单的安装 TypeScript 的方法是通过 npm ，[Node.js Package Manager](https://www.npmjs.com/)。如果你已经安装 npm ,你可以在你的计算机上安装全局 (`-g`) 的 TypeScript ：

```bash
npm install -g typescript
```

You can test your install by checking the version or help.

你可以通过检查版本或帮助来测试安装。

```bash
tsc --version
tsc --help
```

Another option is to install the TypeScript compiler locally in your project (`npm install --save-dev typescript`) and has the benefit of avoiding possible interactions with other TypeScript projects you may have.

另一个选项是在项目中本地安装 TypeScript 编译器 (`npm install --save-dev typescript`)，这有助于避免与你可能拥有的其他 TypeScript 项目进行可能的交互。

### Compiler versus language service 编译器和语言服务

It is important to keep in mind that VS Code's TypeScript language service is separate from your installed TypeScript compiler. You can see the VS Code's TypeScript version in the Status Bar when you open a TypeScript file.

务必记住， VS Code's 的 TypeScript 语言服务与安装的 TypeScript 编译器是分开的。打开 TypeScript 文件时，可以在状态栏中看到 VS Code's 的 TypeScript 版本。

![TypeScript version displayed in the Status Bar](images/compiling/version-status-bar.png)

Later in the article, we'll discuss how you can [change](#using-newer-typescript-versions) the version of TypeScript language service that VS Code uses.

在本文后面，我们将讨论如何使用 VS Code [更改](#using-newer-typescript-versions) TypeScript 语言服务的版本。

## tsconfig.json

Typically the first step in any new TypeScript project is to add in a `tsconfig.json` file. This defines the TypeScript [project settings](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) such as the compiler options and the files that should be included. To do this, open up the folder where you want to store your source and add in a new file named `tsconfig.json`. Once in this file, IntelliSense (`kb(editor.action.triggerSuggest)`) will help you along the way.

通常，任何新的 TypeScript 项目的第一步都是添加 `tsconfig.json` 文件。这将定义 TypeScript 项目设置，如编译器选项和应包含的文件。为此，打开要存储源的文件夹，并添加一个名为 `tsconfig.json` 的新文件。在这个文件中，智能提示 (`kb(editor.action.triggerSuggest)`) 将帮助你完成这一过程。

![tsconfig.json IntelliSense](images/compiling/tsconfigintellisense.png)

A simple `tsconfig.json` looks like this for ES5, **CommonJS** [modules](http://www.commonjs.org/specs/modules/1.0) and source maps:

一个看起来像 ES5、**CommonJS** [模块](http://www.commonjs.org/specs/modules/1.0)和源映射的简单的 `tsconfig.json` 如下所示：

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "sourceMap": true
    }
}
```

Now when you create a `.ts` file as part of the project we will offer up rich editing experiences and syntax validation.

现在，当您创建一个 `.ts` 文件作为项目的一部分时，我们将提供丰富的编辑经验和语法验证。

## Transpile TypeScript into JavaScript 将 TypeScript 转换为 JavaScript

VS Code integrates with `tsc` through our integrated [task runner](/docs/editor/tasks.md). We can use this to transpile `.ts` files into `.js` files. Another benefit of using VS Code tasks is that you get integrated error and warning detection displayed in the [Problems](/docs/editor/editingevolved.md#errors-warnings) panel. Let's walk through transpiling a simple TypeScript Hello World program.

VS Code 将我们完整的任务运行程序结合到 `tsc` 。我们可以使用它将 `.ts` 文件传输到 `.js` 文件中。使用 VS Code 任务的另一个好处是，可以在[问题](/docs/editor/editingevolved.md#errors-warnings)面板中显示集成的错误和警告检测。

### Step 1: Create a simple TS file 第一步:创建一个简单的 TS 文件

Open VS Code on an empty folder and create a `helloworld.ts` file, place the following code in that file...

用 VS Code 打开一个空的文件夹，并创建一个 `helloworld.ts` 文件，将以下代码放入该文件中

```typescript
let message : string = "Hello World";
console.log(message);
```

To test that you have the TypeScript compiler `tsc` installed correctly and a working Hello World program, open a terminal and type `tsc helloworld.ts`. You can use the Integrated Terminal (`kb(workbench.action.terminal.toggleTerminal)`) directly in VS Code.

要测试你是否正确安装了 TypeScript 编译器  `tsc` 和一个正常工作的 Hello World 程序，请打开一个终端并键入 `tsc helloworld.ts`。您可以直接在 VS Code 中使用集成终端 (`kb(workbench.action.terminal.toggleTerminal)`) 。

You should now see the transpiled `helloworld.js` JavaScript file which you can run if you have [Node.js](https://nodejs.org) installed, by typing `node helloworld.js`.

现在，您应该可以看到被转换后的 `helloworld.js` 的 JavaScript 文件，如果安装了 [Node.js](https://nodejs.org) ，可以通过键入 `node helloworld.js` 来运行该文件。

![build and run Hello World](images/compiling/build-hello-world.png)

### Step 2: Run the TypeScript build 第二步:运行构建的 TypeScript 

Execute **Run Build Task** (`kb(workbench.action.tasks.build)`) from the global **Terminal** menu. If you created a `tsconfig.json` file in the earlier section, this should present the following picker:

通过全局**终端**菜单来**构建运行任务** (`kb(workbench.action.tasks.build)`) 。如果您在前面的部分中创建了 `tsconfig.json` 文件，那么将显示以下选择器：

![TypeScript Build](images/compiling/typescript-build.png)

Select the **tsc: build** entry. This will produce a `HelloWorld.js` and `HelloWorld.js.map` file in the workspace.

选择 **tsc: build** 条目。这将会在你的工作区创建一个 `HelloWorld.js` 和 `HelloWorld.js.map` 文件。

If you selected **tsc: watch**, the TypeScript compiler watches for changes to your TypeScript files and runs the transpiler on each change.
如果选择 **tsc: watch**，则 TypeScript 编译器将监视对 TypeScript 文件的更改，并在每次更改时运行转换器。

Under the covers, we run the TypeScript compiler as a task. The command we use is: `tsc -p .`

通过这些操作，我们运行 TypeScript 编译器作为一个任务。我们使用的命令是: `tsc -p .` 。

### Step 3: Make the TypeScript Build the default 第三步:使 TypeScript 构建默认值

You can also define the TypeScript build task as the default build task so that it is executed directly when triggering **Run Build Task** (`kb(workbench.action.tasks.build)`). To do so, select **Configure Default Build Task** from the global **Terminal** menu. This shows you a picker with the available build tasks. Select TypeScript **tsc: build** which generates the following `tasks.json` file in a `.vscode` folder:

你还可以将 TypeScript 构建任务定义为默认构建任务，以便在触发**运行构建任务** (`kb(workbench.action.tasks.build)`) 时直接执行该任务。要执行此操作，请从“全局终端”菜单中选择**配置默认构建任务**。这将向您显示具有可用构建任务的选择器。选择 TypeScript **tsc: build** 它将在 `.vscode` 文件夹中生成 `tasks.json` 文件。

```ts
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "type": "typescript",
            "tsconfig": "tsconfig.json",
            "problemMatcher": [
                "$tsc"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
```

Notice that the task has a `group` JSON object which sets the task `kind` to `build` and makes it the default. Now when you select the **Run Build Task** command or press (`kb(workbench.action.tasks.build)`), you are not prompted to select a task and your compile starts.

请注意，该任务有一个 `group` JSON 对象，它将任务 `kind` 设置为 `build` ，并将其设为默认值。现在，当选择 **运行构建任务** 命令或点击 (`kb(workbench.action.tasks.build)`) 时，系统不会提示您选择任务并开始编译。

> **Tip:** You can also run the program using VS Code's Run/Debug feature. Details about running and debugging Node.js applications in VS Code can be found [here](/docs/nodejs/nodejs-tutorial.md#debugging-your-node-application)

> **Tip:** 您还可以使用VS代码的运行/调试功能来运行程序。可以在 VS Code 中找到有关运行和调试 Node.js 应用程序的详细信息 [here](/docs/nodejs/nodejs-tutorial.md#debugging-your-node-application)

### Step 4: Reviewing build issues 第四步:复查构建问题

The VS Code task system can also detect build issues through a [problem matcher](/docs/editor/tasks.md#defining-a-problem-matcher). A problem matcher parse build output based on the specific build tool and provides integrated issue display and navigation. VS Code ships with many problem matchers and `$tsc` seen above in `tasks.json` is the problem matcher for TypeScript compiler output.

VS Code 任务系统还可以通过[问题匹配器](/docs/editor/tasks.md#defining-a-problem-matcher)检测构建问题。一个问题匹配器基于特定的构建工具解析构建输出，并提供集成的问题显示和导航。VS Code 附带了许多问题匹配器，上面在 `tasks.json` 中看到的 `$tsc` 是 TypeScript 编译器输出的问题匹配器。

As an example, if there was a simple error (extra 'g' in `console.log`) in our TypeScript file, we may get the following output from `tsc`:

    HelloWorld.ts(3,17): error TS2339: Property 'logg' does not exist on type 'Console'.

This would show up in the terminal panel (`kb(workbench.action.terminal.toggleTerminal)`) and selecting the terminal **Tasks - build tsconfig.json** in the terminal view drop-down.

You can see the error and warning counts in the Status Bar. Click on the error and warnings icon to get a list of the problems and navigate to them.

![Error in Status Bar](images/compiling/error-status-bar.png)

You can also use the keyboard to open the list `kb(workbench.actions.view.problems)`.

>**Tip:** Tasks offer rich support for many actions. Check the [Tasks](/docs/editor/tasks.md) topic for more information on how to configure them.

## JavaScript source map support

TypeScript debugging supports JavaScript source maps. To generate source maps for your TypeScript files, compile with the `--sourcemap` option or set the `sourceMap` property in the `tsconfig.json` file to `true`.

In-lined source maps (a source map where the content is stored as a data URL instead of a separate file) are also supported, although in-lined source is not yet supported.

## Output location for generated files

Having the generated JavaScript file in the same folder at the TypeScript source will quickly get cluttered on larger projects. You can specify the output directory for the compiler with the `outDir` attribute.

```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "outDir": "out"
    }
}
```

## Hiding derived JavaScript files

When you are working with TypeScript, you often don’t want to see generated JavaScript files in the File Explorer or in Search results. VS Code offers filtering capabilities with a `files.exclude` [workspace setting](/docs/getstarted/settings.md) (**File** > **Preferences** > **Settings**) and you can easily create an expression to hide those derived files:

`**/*.js: { "when": "$(basename).ts" }`

This pattern will match on any JavaScript file (`**/*.js`) but only if a sibling TypeScript file with the same name is present. The File Explorer will no longer show derived resources for JavaScript if they are compiled to the same location.

![Hiding derived resources](images/compiling/hidingDerivedBefore.png) ![Hiding derived resources](images/compiling/hidingDerivedAfter.png)

To exclude JavaScript files generated from both `.ts` and `.tsx` source files, use this expression:

```json
"**/*.js": { "when": "$(basename).ts" },
"**/**.js": { "when": "$(basename).tsx" }
```

This is a bit of a trick. The search glob pattern is used as a key. The settings above use two different glob patterns to provide two unique keys but the search will still match the same files.

## Using newer TypeScript versions

VS Code ships with a recent stable version of the TypeScript language service and the active version and install location of the TypeScript language service is displayed in the Status Bar when viewing a TypeScript or JavaScript file:

![TypeScript status bar version](images/compiling/status-bar-version.png)

>**Tip:** To get a specific TypeScript version, specify `@version` during npm install. For example, for TypeScript 3.2.0, you would use `npm install --save-dev typescript@3.2.0`. To preview the next version of TypeScript, run `npm install --save-dev typescript@next`.

To use a different TypeScript version by default, configure `typescript.tsdk` in your user [settings](/docs/getstarted/settings.md) to point to a directory containing the TypeScript `tsserver.js` file. You can find the TypeScript installation location using `npm list -g typescript`. The `tsserver.js` file is usually in the `lib` folder.

For example:

```json
{
   "typescript.tsdk": "/usr/local/lib/node_modules/typescript/lib"
}
```

You can also configure a specific version of TypeScript in a particular workspace by adding a `typescript.tsdk` workspace setting pointing to the directory of the `tsserver.js` file:

```json
{
   "typescript.tsdk": "./node_modules/typescript/lib"
}
```

Note that while `typescript.tsdk` points to the `lib` directory inside of `typescript` in these examples, the `typescript` directory must be a full TypeScript install that contains the TypeScript `package.json` file.

### Using the workspace version of TypeScript

If your workspace has a specific TypeScript version, you can switch between the workspace version of TypeScript and the version that VS Code uses by default by opening a TypeScript or JavaScript file in the workspace and clicking on the TypeScript version number in the Status Bar. A message box will appear asking you which version of TypeScript VS Code should use:

![TypeScript version selector](images/compiling/select-ts-version-message.png)

You can switch back to the version of TypeScript that comes with VS Code by clicking on the TypeScript version in the Status Bar again.

## Mixed TypeScript and JavaScript projects

It is possible to have mixed TypeScript and JavaScript projects. To enable JavaScript inside a TypeScript project, you can set the `allowJs` property to `true` in the `tsconfig.json`.

>**Tip:** The `tsc` compiler does not detect the presence of a `jsconfig.json` file automatically. Use the `–p` argument to make `tsc` use your `jsconfig.json` file, e.g. `tsc -p jsconfig.json`.

## Next steps

Read on to find out about:

* [Debugging TypeScript](/docs/typescript/typescript-debugging.md) - Configure the debugger for your TypeScript project.

## Common questions

### How do I resolve a TypeScript "Cannot compile external module" error?

If you get that error, resolve it by creating a `tsconfig.json` file in the root folder of your project. The tsconfig.json file lets you control how Visual Studio Code compiles your TypeScript code. For more information, see the [tsconfig.json overview](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

### Why do I get different errors and warnings with VS Code than when I compile my TypeScript project?

VS Code ships with a recent stable version of the TypeScript language service and it may not match the version of TypeScript installed globally on your computer or locally in your workspace. For that reason, you may see differences between your compiler output and errors detected by the active TypeScript language service. See [Using newer TypeScript versions](/docs/languages/typescript.md#using-newer-typescript-versions) for details on installing a matching TypeScript version.

### Can I use the version of TypeScript that ships with VS 2015?

No, the TypeScript language service which ships with Visual Studio 2015 and 2017 isn't compatible with VS Code. You will need to install a separate version of TypeScript from [npm](https://www.npmjs.com/package/typescript).

### Why are some errors reported as warnings?

By default, VS Code TypeScript displays code style issues as warnings instead of errors. This applies to:

* Variable is declared but never used
* Property is declared but its value is never read
* Unreachable code detected
* Unused label
* Fall through case in switch
* Not all code paths return a value

Treating these as warnings is consistent with other tools, such as TSLint. These will still be displayed as errors when you run `tsc` from the command line.

You can disable this behavior by setting `"typescript.reportStyleChecksAsWarnings": false` in your User [settings](/docs/getstarted/settings.md).
