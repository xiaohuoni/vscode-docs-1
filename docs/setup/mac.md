---
Order: 3
Area: setup
TOCTitle: macOS
ContentId: EEADB50A-F5E3-41E9-89DA-35F165196691
PageTitle: Running Visual Studio Code on macOS
DateApproved: 3/7/2019
MetaDescription: Get Visual Studio Code up and running on Mac (macOS).
---
# Visual Studio Code on macOS (macOS 上的 Visual Studio Code)

## Installation (安装)

1. [Download Visual Studio Code](https://go.microsoft.com/fwlink/?LinkID=534106) for macOS.
2. Double-click on the downloaded archive to expand the contents.
3. Drag `Visual Studio Code.app` to the `Applications` folder, making it available in the `Launchpad`.
4. Add VS Code to your Dock by right-clicking on the icon to bring up the context menu and choosing **Options**, **Keep in Dock**.

1.在 macOS 上[下载 Visual Studio Code](https://go.microsoft.com/fwlink/?LinkID=534106) 
2.双击下载的存档文件以展开内容。
3.将 `Visual Studio Code.app` 拖到 `Applications` 文件夹中，使其在 `Launchpad` 中可用。
4.右键单击图标打开上下文菜单并选择 **Options**, **Keep in Dock**,将 VS Code 添加到 Dock。

## Launching from the command line (从命令行启动)

You can also run VS Code from the terminal by typing 'code' after adding it to the path:

你也可以在添加到路径后通过键入 'code' 从终端运行 VS Code：

- Launch VS Code.
- Open the **Command Palette** (`kb(workbench.action.showCommands)`) and type 'shell command' to find the **Shell Command: Install 'code' command in PATH** command.

- 启动 VS Code。
- 打开 **Command Palette** (`kb(workbench.action.showCommands)`)，键入 'shell command' 以查找 **Shell Command: Install 'code' command in PATH** 命令。

![macOS shell commands](images/mac/shell-command.png)

- Restart the terminal for the new `$PATH` value to take effect. You'll be able to type 'code .' in any folder to start editing files in that folder.

- 重新启动终端以使新的 `$PATH` 值生效。你可以在任何文件夹中键入 'code .' 以开始编辑该文件夹中的文件。

>**Note:** If you still have the old `code` alias in your `.bash_profile` (or equivalent) from an early VS Code version, remove it and replace it by executing the **Shell Command: Install 'code' command in PATH** command.

>**Note:** 如果你在早期的 VS Code 版本的 `.bash_profile`(或等效版本)中仍然有旧的 `code` 别名，请将其删除，并在路径中通过执行 **Shell Command: Install 'code' command in PATH** 命令来替换它。

To manually add VS Code to your path, you can run the following commands:

要手动向路径添加vs代码，可以运行以下命令：

```bash
cat << EOF >> ~/.bash_profile
# Add Visual Studio Code (code)
export PATH="\$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF
```

Start a new terminal to pick up your `.bash_profile` changes.

启动一个新的终端来获取你的 `.bash_profile` 更改。

**Note**: The leading slash `\` is required to prevent `$PATH` from expanding during the concatenation. Remove the leading slash if you want to run the export command directly in a terminal.

**Note**: 在连接过程中，需要使用前导斜杠 `\` 来防止 `$path` 展开。如果要直接在终端中运行 export 命令，请删除前导斜杠。

## Touch Bar support (触摸杆支架)

Out of the box VS Code adds actions to navigate in editor history as well as the full Debug tool bar to control the debugger on your Touch Bar:

开箱即用的 VS Code 添加了导航编辑器历史中的操作，以及在触摸栏上控制调试器的完整调试工具栏：

![macOS Touch Bar](images/mac/touchbar.gif)

## Mojave privacy protections (Mojave 隐私保护)

After upgrading to macOS Mojave version, you may see dialogs saying "Visual Studio Code would like to access your {calendar/contacts/photos}." This is due to the new privacy protections in Mojave and is not specific to VS Code. The same dialogs may be displayed when running other applications as well. The dialog is shown once for each type of personal data and it is fine to choose **Don't Allow** since VS Code does not need access to those folders. You can read a more detailed explanation [here](https://discuss.atom.io/t/why-does-macos-say-that-atom-wants-to-access-my-calendar-contacts-photos-etc).

升级到 MacOS Mojave 版本后，你可能会看到对话框显示 "Visual Studio Code 希望访问你的日历/联系人/照片"。这是由于Mojave中新的隐私保护，不特定于 VS Code。运行其他应用程序时可能也会显示相同的对话框。每个类型的个人数据都会显示一次对话框，选择 **不允许** 是可以的，因为 VS Code 不需要访问这些文件夹。你可以阅读更详细的解释[在这里](https://discuss.atom.io/t/why-does-macos-say-that-atom-wants-to-access-my-calendar-contacts-photos-etc)。

## Updates (更新)

VS Code ships monthly [releases](/updates) and supports auto-update when a new release is available. If you're prompted by VS Code, accept the newest update and it will get installed (you won't need to do anything else to get the latest bits).

VS Code 每月[发布](/updates)一次版本，并在新版本可用时支持自动更新。如果 VS Code 提示你，接受最新的更新，它将被安装(你不需要做任何其他事情来获取最新的位)。

>Note: You can [disable auto-update](/docs/supporting/faq.md#how-do-i-opt-out-of-vs-code-autoupdates) if you prefer to update VS Code on your own schedule.

>Note: 如果你希望按自己的计划更新 VS Code，可以禁用自动更新。

## Preferences menu (首选项菜单)

You can configure VS Code through [settings](/docs/getstarted/settings.md), [color themes](/docs/getstarted/themes.md), and [custom keybindings](/docs/getstarted/keybindings.md) and you will often see mention of the **File** > **Preferences** menu group.  On a macOS, the **Preferences** menu group is under **Code**, not **File**.

你可以通过[设置](/docs/getstarted/settings.md)、[颜色主题](/docs/getstarted/themes.md)和[自定义键绑定](/docs/getstarted/keybindings.md)配置 VS Code，并且经常会看到提到 **File** > **Preferences** 菜单组。在 MacOS 上，**首选项**菜单组位于**代码**下，而不是**文件**。

## Next steps (下一步)

Once you have installed VS Code, these topics will help you learn more about VS Code:

安装完 VS Code 后，这些主题将帮助你了解有关 VS Code 的更多信息：

* [Additional Components](/docs/setup/additional-components.md) - Learn how to install Git, Node.js, TypeScript, and tools like Yeoman.
* [User Interface](/docs/getstarted/userinterface.md) - A quick orientation around VS Code.
* [User/Workspace Settings](/docs/getstarted/settings.md) - Learn how to configure VS Code to your preferences settings.

* [Additional Components](/docs/setup/additional-components.md) - 了解如何安装 Git, Node.js, TypeScript 和类似于 Yeoman 的工具。
* [User Interface](/docs/getstarted/userinterface.md) - 快速定位 VS Code。
* [User/Workspace Settings](/docs/getstarted/settings.md) - 了解如何根据首选项设置配置 VS Code。

## Common questions (常见问题)

### Why do I see "Visual Studio Code would like access to your calendar." (为什么我看到 "Visual Studio Code 希望访问你的日历"。)

If you are running macOS Mojave version, you may see dialogs saying "Visual Studio Code would like to access your {calendar/contacts/photos}." This is due to the new privacy protections in Mojave [discussed above](#mojave-privacy-protections). It is fine to choose **Don't Allow** since VS Code does not need access to those folders.

如果你运行的是 MacOS Mojave 版本，你可能会看到对话框显示 "Visual Studio Code 希望访问你的日历/联系人/照片"。这是由于 Mojave 的新隐私保护[如上所述](#mojave-privacy-protections)。可以选择**不允许**，因为 VS Code 不需要访问这些文件夹。
