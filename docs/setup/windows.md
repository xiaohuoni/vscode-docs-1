---
Order: 4
Area: setup
TOCTitle: Windows
ContentId: 4670C281-5761-46E6-8C46-10D523946FFB
PageTitle: Running Visual Studio Code on Windows
DateApproved: 3/7/2019
MetaDescription: Get Visual Studio Code up and running on Windows
---
# Visual Studio Code on Windows

## Installation (安装)

1. Download the [Visual Studio Code installer](https://go.microsoft.com/fwlink/?LinkID=534107) for Windows.
2. Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe). This will only take a minute.
3. By default, VS Code is installed under `C:\users\{username}\AppData\Local\Programs\Microsoft VS Code`.

1.下载用于 Windows 的 [Visual Studio Code installer](https://go.microsoft.com/fwlink/?LinkID=534107)。
2.下载后，运行安装程序 (VSCodeUserSetup-{version}.exe)。这只需要一分钟。
3.默认情况下，VS Code 安装在 `C:\users\{username}\AppData\Local\Programs\Microsoft VS Code`。

Alternatively, you can also download a [Zip archive](/docs/?dv=winzip), extract it and run Code from there.

或者，你也可以下载一个[压缩文件](/docs/?dv=winzip)，提取它并从中运行代码。

>**Note:** .NET Framework 4.5.2 or higher is required for VS Code.  If you are using Windows 7, make sure you have at least [.NET Framework 4.5.2](https://www.microsoft.com/download/details.aspx?id=42643) installed.

>**Note:** VS Code 需要 .NET Framework 4.5.2 或更高版本。如果你使用的是 Windows7，请确保至少安装了 [.NET Framework 4.5.2](https://www.microsoft.com/download/details.aspx?id=42643) 。

>**Tip:** Setup will add Visual Studio Code to your `%PATH%`, so from the console you can type 'code .' to open VS Code on that folder. You will need to restart your console after the installation for the change to the `%PATH%` environmental variable to take effect.

>**Tip:** 安装程序将向你的 `%PATH%` 添加 Visual Studio Code，因此你可以从控制台键入 'code .' 打开该文件夹上的 VS Code。安装完成后，你需要重新启动控制台，以使对 `%PATH%` 环境变量的更改生效。

## 32 bit versions (32位版本)

If you need to run a 32 bit version of VS Code, both a 32 bit [Installer](https://go.microsoft.com/fwlink/?LinkId=723965) and [Zip archive](https://go.microsoft.com/fwlink/?LinkID=733265) are available.

如果需要运行32位版本的 VS Code，32位[安装程序](https://go.microsoft.com/fwlink/?LinkId=723965)和 [zip 存档](https://go.microsoft.com/fwlink/?LinkID=733265)都可用。

## Updates (更新)

VS Code ships monthly [releases](/updates) and supports auto-update when a new release is available. If you're prompted by VS Code, accept the newest update and it will be installed (you won't need to do anything else to get the latest bits).

VS Code 每月[发布](/updates)一次版本，并在新版本可用时支持自动更新。如果收到vs code的提示，接受最新的更新，它将被安装(你不需要做任何其他事情来获取最新的位)。

>Note: You can [disable auto-update](/docs/supporting/faq.md#how-do-i-opt-out-of-vs-code-autoupdates) if you prefer to update VS Code on your own schedule.

>Note: 如果你希望按自己的计划更新vs代码，可以[禁用自动更新](/docs/supporting/faq.md#how-do-i-opt-out-of-vs-code-autoupdates)。

## Next steps (下一步)

Once you have installed VS Code, these topics will help you learn more about VS Code:

一旦安装了 VS Code，这些主题将帮助你了解有关 VS Code 的更多信息：

* [Additional Components](/docs/setup/additional-components.md) - Learn how to install Git, Node.js, TypeScript and tools like Yeoman.
* [User Interface](/docs/getstarted/userinterface.md) - A quick orientation to VS Code.
* [User/Workspace Settings](/docs/getstarted/settings.md) - Learn how to configure VS Code to your preferences through settings.
* [Tips and Tricks](/docs/getstarted/tips-and-tricks.md) - Lets you jump right in and learn how to be productive with VS Code.

* [Additional Components](/docs/setup/additional-components.md) - 了解如何安装 Git, Node.js, TypeScript 和 Yeoman 等工具。
* [User Interface](/docs/getstarted/userinterface.md) - 对 VS Code 的快速定位。
* [User/Workspace Settings](/docs/getstarted/settings.md) - 了解如何通过设置将 VS Code 配置为你的首选项。
* [Tips and Tricks](/docs/getstarted/tips-and-tricks.md) - 让你直接进入并学习如何使用 VS Code 提高效率。

## Common questions (常见问题)

### What command line arguments are supported by the Windows Setup? (Windows 安装程序支持哪些命令行参数？)

VS Code uses [Inno Setup](http://www.jrsoftware.org/isinfo.php) to create its setup package
for Windows. Thus, all the [Inno Setup command line switches](http://www.jrsoftware.org/ishelp/index.php?topic=setupcmdline) are available for use.

VS Code 使用 [Inno Setup](http://www.jrsoftware.org/isinfo.php) 为 Windows 创建其安装包。因此，所有 [Inno Setup 命令行开关](http://www.jrsoftware.org/ishelp/index.php?topic=setupcmdline)都可以使用。

Additionally, you can prevent the Setup from launching VS Code after completion with `/mergetasks=!runcode`.

此外，你可以阻止安装程序在完成后通过 `/mergetasks=!runcode` 启动 VS Code。

### Scrolling is laggy and not smooth (滚动缓慢且不平滑)

On certain devices, editor scrolling is not smooth but laggy for an unpleasant experience. If you notice this issue, make sure you install the Windows 10 October 2018 update where this issue is fixed.

在某些设备上，编辑器滚动不是平滑的，但对于不愉快的体验是滞后的。如果你注意到此问题，请确保已安装或更新 Windows 到2018年10月10日，那么你的问题就解决了。

### I'm having trouble with the installer (安装程序有问题)

Try using the [zip file](/docs/?dv=winzip) instead of the installer.  To use this, unzip VS Code in your `AppData\Local\Programs` folder.

尝试使用 [zip文件](/docs/?dv=winzip)而不是安装程序。使用此代码，解压 VS Code 到 `AppData\Local\Programs` 文件夹下。

>**Note:** When VS Code is installed via a Zip file, you will need to manually update it for each [release](/updates).

>**Note:** 当通过 Zip 文件安装 VS Code 时，你需要为每个[版本](/updates)手动更新它。

### Icons are missing (图标丢失)

I installed Visual Studio Code on my Windows 7 or 8 machine. Why are some icons not appearing in the workbench and editor?

我在Windows7或8计算机上安装了 Visual Studio Code。为什么有些图标没有出现在工作台和编辑器中？

VS Code uses [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) icons and we have found instances where the .SVG file extension is associated with something other than `image/svg+xml`. We're considering options to fix it, but for now here's a workaround:

VS Code 使用 [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) 图标，我们发现了一些实例，其中 .SVG 文件扩展名与 `image/svg+xml` 以外的内容相关联。我们正在考虑解决问题的方法，但现在有一个解决方法：

Using the Command Prompt:

使用命令提示：

1. Open an Administrator Command Prompt.
2. Type `REG ADD HKCR\.svg /f /v "Content Type" /t REG_SZ /d image/svg+xml`.

1.打开管理员命令提示。
2.输入 `REG ADD HKCR\.svg /f /v "Content Type" /t REG_SZ /d image/svg+xml`。

Using the Registry Editor (regedit):

使用注册表编辑器 (regedit)：

1. Start `regedit`.
2. Open the `HKEY_CLASSES_ROOT` key.
3. Find the `.svg` key.
4. Set its `Content Type` Data value to `image/svg+xml`.
5. Exit `regedit`.

1.开始 `regedit`。
2.打开 `HKEY_CLASSES_ROOT` 键。
3.找到 `.svg` 键。
4.将其 `Content Type` 数据值设置为 `image/svg+xml`。
5.退出 `regedit`。

