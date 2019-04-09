---
TOCTitle: FAQ
ContentId: E02F97FD-842B-4D27-B461-37DD18B2582E
PageTitle: Visual Studio Code Frequently Asked Questions
DateApproved: 3/7/2019
MetaDescription: Visual Studio Code Frequently Asked Questions
---
# Visual Studio Code FAQ  (Visual Studio Code 常见问题解答)

Our docs contain a **Common questions** section as needed for specific topics. We've captured items here that don't fit in the other topics.

我们的文档包含一个**常见问题**部分，用于特定主题。我们在这里注意到了不适合其他主题的项目。

If you don't see an answer to your question here, check our previously [reported issues](https://github.com/microsoft/vscode/issues) and our [Updates](/updates) notes.

如果你在这里看不到问题的答案，请查看我们以前报告的[问题](https://github.com/microsoft/vscode/issues) 和[更新](/updates)说明。

## What is the difference between VS Code and VS Community? (VS Code 和 VS Community 有什么区别?)

Visual Studio Code is a streamlined code editor with support for development operations like debugging, task running and version control. It aims to provide just the tools a developer needs for a quick code-build-debug cycle and leaves more complex workflows to fuller featured IDEs.

Visual Studio Code 是一个简化的代码编辑器，支持调试、任务运行和版本控制等开发操作。它旨在为开发人员提供快速代码构建调试周期所需的工具，并将更复杂的工作流留给功能更丰富的 IDE。

## Which OS's are supported? (支持哪些操作系统?)

VS Code runs on macOS, Linux, and Windows. See [Requirements](requirements) for the supported versions. You can find more platform specific details under [SETUP](/docs/setup/setup-overview.md).

VS Code 运行在 MacOS、Linux 和 Windows 上。请参阅支持版本的[要求](requirements)。你可以在 [SETUP](/docs/setup/setup-overview.md) 下找到更多特定于平台的详细信息。

## Is VS Code free? (VS Code 使免费的吗？)

Yes, VS Code is [free for private or commercial use](https://code.visualstudio.com/license).

是的，VS Code 可供[私人或商业使用](https://code.visualstudio.com/license)。

## Report an issue with a VS Code extension (报告带有 VS Code 扩展的问题)

For bugs, feature requests or to contact an extension author, you should use the links available in the Visual Studio Code [Marketplace](https://marketplace.visualstudio.com/vscode) or use **Help: Report Issue** from the Command Palette. However, if there is an issue where an extension does not follow our code of conduct, for example it includes profanity, pornography or presents a risk to the user, then we have an email alias where you can [contact us to report the issue](mailto:VSMarketplace@microsoft.com). Once the mail is received, our Marketplace team will look into an appropriate course of action, up to and including unpublishing the extension.

对于错误、功能请求或与扩展作者联系，应使用 Visual Studio Code [市场](https://marketplace.visualstudio.com/vscode)中提供的链接，或使用命令调色板中的**帮助：报告问题**。但是，如果存在扩展不遵守我们的行为准则的问题，例如它包括亵渎、色情或对用户造成风险，那么我们有一个电子邮件别名，你可以在其中[联系我们报告该问题](mailto:VSMarketplace@microsoft.com)。一旦收到邮件，我们的市场团队将调查适当的行动过程，包括取消发布扩展。

## How do I find the VS Code version? (如何找到 VS Code 版本?)

You can find the VS Code version information in the About dialog box.

你可以在 "About" 对话框中找到 VS Code 版本信息。

On macOS, go to **Code** > **About Visual Studio Code**.

在 macOS，进入 **Code** > **About Visual Studio Code**。

On Windows and Linux, go to **Help** > **About**.

在 Windows 和 Linux，进入 **Help** > **About**。

The VS Code version is the first **Version** number listed and has the version format 'major.minor.release', for example '1.27.0'.

VS Code 版本是列出的第一个**版本**号，版本格式为 'major.minor.release'，例如 '1.27.0'。

## How do I opt out of VS Code auto-updates? (如何选择退出 VS Code 自动更新？)

By default, VS Code is set up to auto-update for macOS and Windows users when we release new updates. If you do not want to get automatic updates, you can set the **Update: Mode** setting from `default` to `none`.

默认情况下，当我们发布新的更新时，VS Code 会为用户设置为 MacOS 和 Windows 自动更新。如果不想获得自动更新，可以将 **Update: Mode** 设置从 `default` 设置为 `none`。

To modify the update mode, go to **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**), search for `update mode` and change the setting to `none`.

修改更新模式，路径为 **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**)，搜索 `update mode`并将设置更改为 `none`。

If you use the JSON editor for your settings, add the following line:

如果使用 JSON 编辑器进行设置，请添加以下行：

```json
    "update.mode": "none"
```

You can install a previous release of VS Code by uninstalling your current version and then installing the download provided at the top of a specific release page under [Updates](/updates).

你可以通过卸载当前版本，然后安装[更新](/updates)下特定版本页面顶部提供的下载来安装先前版本的 VS Code 。

>**Note:** On Linux: If the VS Code repository was installed correctly then your system package manager should handle auto-updating in the same way as other packages on the system. See [Installing VS Code on Linux](/docs/setup/linux.md#updates).

>**Note:** On Linux:如果正确安装了 VS Code 存储库，则系统包管理器应以与系统上其他包相同的方式处理自动更新。查看[在 Linux 上安装 VS Code](/docs/setup/linux.md#updates)。

## Can I run a portable version of VS Code? (我能运行 VS Code 的便携式版本吗?)

Yes, VS Code has a [Portable Mode](/docs/editor/portable.md) which lets you keep settings and data in the same location as your installation, for example, on a USB drive.

是的，VS Code 有一个[便携模式](/docs/editor/portable.md)，允许你将设置和数据保存在与安装相同的位置，例如，在USB驱动器上。

## Licensing (许可)

### Location (位置)

You can find the VS Code licenses, third party notices and [Chromium](https://www.chromium.org) Open Source credit list under your VS Code installation location `resources\app` folder. VS Code's `ThirdPartyNotices.txt`, Chromium's `Credits_*.html`, and VS Code's English language `LICENSE.txt` are available under `resources\app`. Localized versions of `LICENSE.txt` by Language ID are under `resources\app\licenses`.

你可以在 VS Code 安装本地 `resources\app` 文件夹下找到 VS Code 许可证、第三方通知和 [chromium](https://www.chromium.org) 开源信用列表。VS Code 的 `ThirdPartyNotices.txt`、Chromium 的 `Credits_*.html` 和 VS Code 的英语 `LICENSE.txt` 可在 `resources\app` 下找到。语言ID 的 `LICENSE.txt` 本地化版本位于 `resources\app\licenses` 下。

### Why does Visual Studio Code have a different license than the vscode GitHub repository? (为什么 Visual Studio Code 具有与 vscode GitHub存储库不同的许可证？)

To learn why Visual Studio Code, the product, has a different license than vscode, the open source [GitHub repository](https://github.com/microsoft/vscode), see [issue #60](https://github.com/Microsoft/vscode/issues/60#issuecomment-161792005) for a detailed explanation.

要了解产品 Visual Studio Code 与开源 [Github 存储库](https://github.com/microsoft/vscode) vscode 具有不同许可证的原因，请参阅[第60版](https://github.com/Microsoft/vscode/issues/60#issuecomment-161792005)以获取详细说明。

## Can I run prerelease versions of VS Code? (我能运行 VS Code 的预发布版本吗?)

Want an early peek at new VS Code features?  You can try prerelease versions of VS Code by installing the "Insiders" build.  The Insiders build installs side by side to your stable VS Code install and has isolated settings, configurations and extensions.  The Insiders build is updated nightly so you'll get the latest bug fixes and feature updates from the day before.

想早点了解新的 VS Code 特性吗？你可以通过安装 "insiders" 编译来尝试预发布版本的 VS Code。内部人员构建与稳定的vs代码并排安装，并具有独立的设置、配置和扩展。内部人员构建是每晚更新的，因此你可以从前一天获得最新的 bug 修复和功能更新。

To install the Insiders build, go to the Insiders [download page](/insiders).

要安装Insiders Build，请转到 [Insiders下载页](/insiders)。

## VS Code gets unresponsive right after opening a folder (打开文件夹后，VS Code 将立即停止响应)

When you open a folder, VS Code will search for typical project files to offer you additional tooling (e.g. the solution picker in the status bar to open a solution). If you open a folder with lots of files, the search can take a large amount of time and CPU resources during which VS Code might be slow to respond. We plan to improve this in the future but for now you can exclude folders from the explorer via the `files.exclude` setting and they will not be searched for project files:

当你打开文件夹，VS Code 会搜索典型项目文件提供额外的工具(例如你的解决方案选择在状态栏打开一个解决方案)。如果打开的文件夹中有大量文件，搜索可能会花费大量时间和 CPU 资源，在此期间，VS Code 的响应速度可能会很慢。我们计划在将来对此进行改进，但现在你可以通过 `files.exclude` 设置从资源管理器中排除文件夹，并且不会在其中搜索项目文件：

```json
    "files.exclude": {
        "**/largeFolder": true
    }
```

## VS Code is blank? (VS Code 为空？)

The Electron shell used by Visual Studio Code has trouble with some GPU (graphics processing unit) hardware acceleration. If VS Code is displaying a blank (empty) main window, you can try disabling GPU acceleration when launching VS Code by adding the Electron `--disable-gpu` command line switch.

Visual Studio Code 使用的电子外壳存在一些 GPU (图形处理单元)硬件加速问题。如果 VS Code 显示一个空白的主窗口，则可以尝试在启动 VS Code 时禁用 GPU 加速，方法是添加 `--disable-gpu` 命令行开关。

```bash
code --disable-gpu
```

## Blurriness on macOS Mojave (macOS Mojave 的模糊程度)

If you have updated to macOS 10.14 (Mojave), you might have noticed that fonts in VS Code look blurry if you are not using a high-DPI monitor.

如果你已经更新到 MacOS10.14 (Mojave)，那么你可能会注意到，如果你不使用高 DPI 监视器，VS Code 中的字体看起来很模糊。

A workaround for this is to run:

解决方法是运行：

```bash
defaults write com.microsoft.VSCode.helper CGFontRenderingFontSmoothingDisabled -bool NO
```

from a terminal followed by restarting your computer.

从终端重新启动计算机。

Note that this change is global for every application and not specific to VS Code. See [issue 51132](https://github.com/Microsoft/vscode/issues/51132) for the related discussion.

请注意，此更改对于每个应用程序都是全局的，而不是特定于 VS Code。相关讨论见 [issue 51132](https://github.com/Microsoft/vscode/issues/51132)。

## Installation appears to be corrupt [Unsupported] (安装似乎已损坏[不支持])

VS Code does a background check to detect if the installation has been changed on disk and if so, you will see the text '[Unsupported]' in the title bar. This is done since some extensions directly modify (patch) the VS Code product in such a way that is semi-permanent (until the next update) and this can cause hard to reproduce issues. We are not trying to block VS Code patching, but we want to raise awareness that patching VS Code means you are running an unsupported version. Reinstalling VS Code will replace the modified files and silence the warning.

VS Code 进行后台检查，以检测磁盘上的安装是否已更改，如果已更改，你将在标题栏中看到文本 '[Unsupported]'。这是因为一些扩展直接修改(修补) VS Code 产品的方式是半永久的(直到下一次更新)，这可能导致难以重现的问题。我们不想阻止 VS Code 修补，但我们想提高认识，修补 VS Code 意味着你运行的是不受支持的版本。重新安装 VS Code 将替换修改过的文件并使警告静音。

## GDPR and VS Code (GDPR 和 VS Code)

As the General Data Protection Regulation comes into effect, we want to take this opportunity to reiterate that we take privacy very seriously.  That's both for Microsoft as a company and specifically within the VS Code team.

随着通用数据保护条例的生效，我们希望借此机会重申，我们非常重视隐私。这对于微软来说是一个公司，特别是在 VS Code 团队中。

VS Code does collect telemetry data which we use to help understand how to improve the product.  For example, it helps debug issues such as slow start-up times and prioritize features.  While we appreciate this insight, we also know that not everyone wants to send this data, so we continue to offer the ability to disable telemetry as outlined [here](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

VS Code 收集遥测数据，我们使用这些数据来帮助理解如何改进产品。例如，它有助于调试问题，例如启动时间慢和特性的优先级。虽然我们很欣赏这种见解，但我们也知道并非每个人都想发送这些数据，因此我们继续提供禁用遥测功能的能力，如前所述 [here](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)。

In preparation for GDPR, we have made several updates to VS Code, these include:

为了准备 GDPR，我们对 VS Code 进行了几次更新，这些更新包括：

* Making it easier to opt out of telemetry collection by placing a notification in product for all existing and new users.
* Reviewing and classifying the telemetry that we send (which is documented in [our OSS codebase](https://github.com/Microsoft/vscode/pull/34997)).
* Ensuring that we have valid data retention policies in place for any data we do collect, for example crash dumps.

* 通过在产品中为所有现有用户和新用户放置通知，可以更容易地选择退出遥测采集。
* 审查和分类我们发送的遥测(记录在[我们的 OSS 代码库](https://github.com/Microsoft/vscode/pull/34997)中)
* 确保我们为收集的任何数据(例如崩溃转储)制定了有效的数据保留策略。

In short, we have worked hard to do the right thing, for all users, as these practices apply to all geographies, not just Europe.

简而言之，我们努力为所有用户做正确的事情，因为这些实践适用于所有地区，而不仅仅是欧洲。

One question we expect people to ask is to see the data we collect. However, we don't have a reliable way to do this as VS Code does not have is a 'sign-in' experience that would uniquely identify a user.  We do send information which helps us approximate a single user for diagnostic purposes (this is based on a hash of the network adapter NIC) but this is not guaranteed to be unique. For example, VM's often rotate NIC ID's or allocate from a pool.  This technique is sufficient to help us when working through problems, but it is not reliable enough for us to 'provide your data'.

我们希望人们问的一个问题是看到我们收集的数据。但是，我们没有可靠的方法来做到这一点，因为 VS Code 没有一种'登录'体验，可以唯一地标识用户。我们确实发送了一些信息，这些信息有助于我们在诊断时估计一个用户(这是基于网络适配器 NIC 的散列值)，但这并不能保证是唯一的。例如，虚拟机经常旋转 NIC ID 或从池中分配。这项技术足以帮助我们解决问题，但我们"提供你的数据"还不够可靠。

In conclusion, we expect our approach to evolve as we learn more about GDPR and the expectations of our users.  We greatly appreciate the data users do send to us, as it is very valuable, VS Code is a better product for everyone because it.  And again, if you are worried about privacy, we offer the ability to disable sending telemetry as described [here](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

总之，我们希望我们的方法随着我们对 GDPR 和用户期望了解的更多而不断发展。我们非常感谢用户发送给我们的数据，因为它是非常有价值的，而对每个人来说，VS Code 是一个更好的产品，因为它。同样，如果你担心隐私，我们提供禁用发送遥测的功能，如前所述 [here](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)。

You can find more information about how the Visual Studio family approaches GDPR at [Visual Studio Family Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-visual-studio-family).

你可以在 [Visual Studio 系列数据主题请求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-visual-studio-family)中找到有关 Visual Studio 系列如何处理 GDPR 的更多信息。

## How to disable telemetry reporting (如何禁用遥测报告)

VS Code collects usage data and sends it to Microsoft to help improve our products and services. Read our [privacy statement](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409) to learn more.

VS Code 收集使用数据并将其发送给 Microsoft，以帮助改进我们的产品和服务。阅读我们的[隐私声明](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409)了解更多信息。

If you don't wish to send usage data to Microsoft, you can set the `telemetry.enableTelemetry` setting to `false`.

如果不希望向 Microsoft 发送使用数据，可以将 `telemetry.enableTelemetry` 设置为 `false`。

From **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**), search for `telemetry.enableTelemetry` and uncheck the setting. This will silence all telemetry events from VS Code going forward. Telemetry information may have been collected and sent up until the point when you disable the setting.

从 **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**)，搜索Telemetry.EnableTelemetry并取消选中该设置。这将会默默的推进 VS Code 的遥测事件。遥测信息可能已收集并发送到禁用设置时为止。

If you use the JSON editor for your settings, add the following line:

如果使用 JSON 编辑器进行设置，请添加以下行：

```json
    "telemetry.enableTelemetry": false
```

You can inspect telemetry events in the Output panel by setting the log level to **Trace** using **Developer: Set Log Level** from the Command Palette.

你可以使用命令调色板中的 **developer:set log level** 将日志级别设置为 **trace**，在输出面板中检查遥测事件。

> **Important Notice**: VS Code gives you the option to install Microsoft and third party extensions. These extensions may be collecting their own usage data and are not controlled by the `telemetry.enableTelemetry` setting. Consult the specific extension's documentation to learn about its telemetry reporting.

> **Important Notice**: VS代码为你提供了安装 Microsoft 和第三方扩展的选项。这些扩展可能正在收集自己的使用数据，并且不受 `telemetry.enableTelemetry` 设置的控制。请参阅特定扩展的文档以了解其遥测报告。

## How to disable crash reporting (如何禁用崩溃报告)

VS Code collects data about any crashes that occur and sends it to Microsoft to help improve our products and services. Read our [privacy statement](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409) to learn more.

VS Code 收集所有发生崩溃的数据，并将其发送给 Microsoft，以帮助改进我们的产品和服务。阅读我们的[隐私声明](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409)了解更多信息。

If you don't wish to send crash data to Microsoft, you can set the `telemetry.enableCrashReporter` setting to `false`.

如果不希望将崩溃数据发送到 Microsoft，可以将 `telemetry.enableCrashReporter` 设置为 `false`。

From **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**), search for `telemetry.enableCrashReporter` and uncheck the setting.

从 **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**),搜索 `telemetry.enableCrashReporter`  并取消选中该设置。

If you use the JSON editor for your settings, add the following line:

如果使用 JSON 编辑器进行设置，请添加以下行：

```json
    "telemetry.enableCrashReporter": false
```

> **Important Notice**: This option requires a restart of VS Code to take effect.

> **重要提示**: 此选项需要重新启动 VS Code 才能生效。

## Managing online services (管理在线服务)

Beyond crash reporting and telemetry, VS Code uses online services for various other purposes such as downloading product updates, finding, installing and updating extensions, or providing Natural Language Search within Settings. You can choose to turn on/off features that use these services.

除了故障报告和遥测之外，VS Code 还将在线服务用于各种其他用途，例如下载产品更新、查找、安装和更新扩展，或在设置中提供自然语言搜索。你可以选择打开/关闭使用这些服务的功能。

Please note, that turning off these features does not put VS Code into offline mode. If, for example, you search for extensions in the **Extensions** view, VS Code still searches the online VS Code Marketplace. The settings ensure that VS Code does not talk to online services without you requesting it.

请注意，关闭这些功能不会使 VS Code 进入脱机模式。例如，如果你在**扩展**视图中搜索扩展，那么 VS Code 仍然会搜索在线 VS Code Marketplace。这些设置确保在没有你请求的情况下， VS Code 不会与联机服务通信。

From **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**), and search for `@tag:usesOnlineServices`. This will display all settings that control the usage of online services and you can individually switch them on or off.

从 **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**) 查找 `@tag:usesOnlineServices`。这将显示控制联机服务使用的所有设置，你可以单独打开或关闭这些设置。

> **Important Notice**: VS Code gives you the option to install Microsoft and third party extensions. These extensions may also use online services and may not provide settings to configure the usage of these online services, or they may not register their settings to show up when searching for `@tag:usesOnlineServices`. Consult the specific extension's documentation to learn about its usage of online services.

> **重要提示**:  VS Code 为你提供了安装 Microsoft 和第三方扩展的选项。这些扩展还可能使用联机服务，并且可能不提供配置这些联机服务使用的设置，或者在搜索 `@tag:usesOnlineServices` 时，它们可能不注册要显示的设置。请参阅特定扩展的文档以了解其联机服务的使用情况。

## What non-Microsoft online services does VS Code talk to (VS Code 对非微软在线服务说了什么)

The built-in **npm support for VS Code** extension sends requests to `https://registry.npmjs.org` and `https://registry.bower.io`.

内置的 **npm 对 VS Code 支持**的扩展将请求发送到 `https://registry.npmjs.org` 和 `https://registry.bower.io`。

The built-in **TypeScript and JavaScript Language Features** extension queries the `@types` domain at `https://registry.npmjs.org`.

内置的 **TypeScript 和 JavaScript 语言特征**的扩展在 `https://registry.npmjs.org` 上查询 `@types` 域。

When you use **Developer: Toggle Developer Tools** or **Developer: Open Webview Developer Tools**, VS Code may talk to Google servers to fetch data needed to launch Developer Tools.

使用 **Developer: Toggle Developer Tools** 或者 **Developer: Open Webview Developer Tools** 时，VS Code 可能会与 Google 服务器进行对话，以获取启动 Developer Tools 所需的数据。

## Do you send all my information to a recommendation service? (你会把我所有的信息都寄到推荐服务机构吗?)

VS Code provides extension recommendations based on your file types, your workspace, and your environment. File type recommendations are either precomputed or dynamic. Workspace and environment recommendations are always precomputed.

VS Code 根据文件类型、工作区和环境提供扩展建议。文件类型建议要么是预计算的，要么是动态的。工作区和环境建议总是预先计算的。

If you want to know why an extension is being recommended, open the extension's detail page. You can find the recommendation reason in the page header.

如果你想知道推荐扩展名的原因，请打开扩展名的详细信息页。你可以在页面标题中找到推荐原因。

### Dynamic recommendations (动态建议)

When you open a file type for which VS Code does not have any precomputed recommendation, it asks the extension Marketplace for extensions that declare that they support this file type. If the query returns extensions you don't have installed, VS Code tells you about it.

当你打开一个 VS Code 没有任何预计算建议的文件类型时，它会向扩展市场询问声明支持此文件类型的扩展名。如果查询返回未安装的扩展名，那么 VS Code 会告诉你有关扩展名的信息。

### Precomputed recommendations (预先计算的建议)

VS Code collects telemetry about which extensions are being activated for what file types and what workspaces/folders. We identify folders by computing a hash of each of the folder's Git remotes.

VS Code 会收集遥测信息，以确定哪些扩展正在为哪些文件类型和哪些工作区/文件夹激活。我们通过计算每个文件夹的 Git 远程的散列来识别文件夹。

We use this information to precompute anonymous recommendations. Precomputed recommendations are instructions that spell out under which conditions an extension should be recommended. For example, when we see an interesting co-relation between two extensions A and B, one instruction might be: Recommend extension B if the user has installed extension A but not B.

我们使用此信息预计算匿名建议。预先计算的建议是说明在何种条件下应建议扩展的指令。例如，当我们看到两个扩展 A 和 B 之间有一个有趣的共同关系时，一条指令可能是：如果用户安装了扩展 A 而不是 B，那么建议使用扩展 B。

Some precomputed recommendations are shipped as part of the product while additional precomputed recommendations are fetched at runtime from an online Microsoft service. VS Code independently evaluates and executes precomputed recommendations without sending any user information to any online service.

一些预计算的建议作为产品的一部分提供，而其他预计算的建议则在运行时从联机 Microsoft 服务中获取。VS Code 独立地评估和执行预先计算的建议，而不向任何在线服务发送任何用户信息。

## Technical Support (技术支持)

You can ask questions and search for answers on [Stack Overflow](https://stackoverflow.com/questions/tagged/vscode) and enter issues and feature requests directly in our [GitHub repository](https://github.com/Microsoft/vscode/blob/master/CONTRIBUTING.md).

你可以在[堆栈溢出](https://stackoverflow.com/questions/tagged/vscode)时提出问题并搜索答案，并直接在 [Github](https://github.com/Microsoft/vscode/blob/master/CONTRIBUTING.md) 存储库中输入问题和特性请求。

If you'd like to contact a professional support engineer, you can open a ticket with the [Microsoft assisted support team](https://support.microsoft.com/assistedsupportproducts).

如果你要联系专业支持工程师，可以与 [Microsoft 辅助支持团队](https://support.microsoft.com/assistedsupportproducts)一起开罚单。
