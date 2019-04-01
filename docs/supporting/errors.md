---
Order:
TOCTitle: Error Codes
ContentId: 343B5C4D-3473-4454-AD22-084F405D6905
PageTitle: Visual Studio Code workarounds for errors you might hit in the product.
DateApproved: 3/7/2019
MetaDescription: Several error conditions can easily be resolved by the user this page is designed to help un-block you.
---
# Common Error Cases  常见错误案例

Some errors that occur when using Visual Studio Code can be worked around or resolved by you. This topic describes several common error conditions, listed by error code number, and what you can do to resolve them.

使用 Visual Studio Code 时发生的一些错误可以由你自己解决。本主题描述了按错误代码编号列出的几个常见错误条件，以及可以如何解决它们。

## 20002

**Error:** Cannot find '/usr/bin/gnome-terminal' for launching your Node.js program

**Error:** 找不到用于启动 Node.js 程序的 '/usr/bin/gnome-terminal'

On Linux, the VS Code Node.js debugger requires the [gnome-terminal](https://help.gnome.org/users/gnome-terminal/stable/) emulator for launching the Node.js program. If gnome-terminal is not installed, the VS Code debugger cannot launch your program for debugging.

在 Linux 上，VS Code Node.js 调试器需要 [gnome-terminal](https://help.gnome.org/users/gnome-terminal/stable/) 模拟器来启动 Node.js 程序。

There are two options for solving this problem: 解决这个问题有两种选择:

* Install the gnome-terminal by running the command `sudo apt-get install gnome-terminal` (or the equivalent of your Linux distribution).
* Manually launch your program in debug mode by passing a `--inspect` or `--inspect-brk` option to Node.js and then attach the VS Code debugger to port 9229 on 'localhost'.

* 通过运行命令 `sudo apt-get install gnome-terminal` (或相当于 Linux 发行版) 来安装 gnome-terminal。
* 在 debug 模式下手动启动程序，方法是将 `--inspect` 或 `--inspect-brk` 选项传递给 Node.js ，然后将 VS Code 调试程序附加到 'localhost' 上的端口9229。

## 20003

**Error:** Attribute 'program' is not absolute; consider adding '${workspaceFolder}/' as a prefix to make it absolute.

**Error:** 属性 'program' 不是绝对的；请考虑添加 '${workspaceFolder}/' 作为前缀，使其成为绝对的。

This error occurs when you have a relative path in your [debug configuration](/docs/editor/debugging.md#launch-configurations) `launch.json` file (located in your workspace `.vscode` directory).

当你在 [debug configuration](/docs/editor/debugging.md#launch-configurations) `launch.json` 文件中有相对路径时，就会发生此错误。

In the example below, the `program` attribute has a relative path to `app.js` at the root of the workspace (project folder).

在下面的示例中，`program` 属性在工作区 ( project 文件夹) 的根目录中具有到 `app.js` 的相对路径。

```json
{
"version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "./app.js"
        }
    ]
}
```

The fix is to use an absolute path or better use the `${workspaceFolder}` variable which will resolve to the absolute path of the project folder.

修复方法是使用绝对路径，或者更好地使用 `${workspaceFolder}` 变量，该变量将解析为项目文件夹的绝对路径。

```json
{
"version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "${workspaceFolder}/app.js"
        }
    ]
}
```

By using the `${workspaceFolder}` variable, you won't need to update the absolute path if the project is moved or shared with other developers.

通过使用 `${workspaceFolder}` 变量，如果项目被移动或与其他开发人员共享，则不需要更新绝对路径。

In previous versions of VS Code, you were allowed to use relative paths in your launch configurations but this was problematic. VS Code now warns you about relative paths when you start a debugging session and recommends prefixing the relative path with `${workspaceFolder}/`. VS Code also checks other path attributes, such as `cwd` (current working directory), `outFiles` (location of other JavaScript files), and `runtimeExecutable`.

在先前版本的 VS Code 中，允许你在启动配置中使用相对路径，但这是有问题的。现在，当你启动调试会话时， VS Code 会警告你有关相对路径的问题，并建议使用 `${workspaceFolder}/` ，对相对路径进行前缀。 VS Code 也会检查的代码路径和其他属性，如 `cwd` (当前工作目录)， `outFiles` (其他 JavaScript 文件的位置)的位置，和 `runtimeExecutable`。

> **Tip:** See the VS Code [debugging](/docs/editor/debugging.md) documentation for more information about `launch.json`, [debugger configuration](/docs/editor/debugging.md#launch-configurations), and [variable substitution](/docs/editor/variables-reference.md).

> **Tip:** 有关 `launch.json` 、[调试器配置](/docs/editor/debugging.md#launch-configurations)和[变量替换](/docs/editor/variables-reference.md) 的详细信息，请参阅 VS Code 调试文档。

## Didn't find a solution?  找不到解决方案？

### GitHub issues GitHub 问题

If the steps above don't help you, you may have hit a bug. You can check our [reported issues](https://github.com/microsoft/vscode/issues) to see if others have reported the same issue.

如果以上步骤对你没有帮助，你可能遇到了一个错误。你可以检查我们[报告的问题](https://github.com/microsoft/vscode/issues) ，看看其他人是否报告了相同的问题。

### Online search 在线搜索

You can also search the rest of our online [documentation](/docs) for answers in our main topics and **Common questions** sections. The online **Search** control is located in the upper right of the [code.visualstudio.com](/docs) website.

你也可以在我们的其他在线[文档](/docs)中搜索我们的主要主题和**常见问题**部分的答案。在线**搜索**控件位于 [code.visualstudio.com](/docs) 网站的右上角。

### Stack Overflow 栈溢出

There is also an active VS Code [Stack Overflow channel](https://go.microsoft.com/fwlink/?LinkID=536384) where you can browse answers or ask a question.

还有一个起作用的 VS Code [栈溢出通道](https://go.microsoft.com/fwlink/?LinkID=536384) ，你可以在其中浏览答案或提出问题。

