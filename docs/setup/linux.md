---
Order: 2
Area: setup
TOCTitle: Linux
ContentId: 7FDF94DB-3527-4296-BE1C-493495B89408
PageTitle: Running Visual Studio Code on Linux
DateApproved: 3/7/2019
MetaDescription: Get Visual Studio Code up and running on Linux.
---
# Visual Studio Code on Linux 

## Installation (安装)

### Debian and Ubuntu based distributions (基于 Debian 和 Ubuntu 的发行版)

The easiest way to install Visual Studio Code for Debian/Ubuntu based distributions is to download and install the [.deb package (64-bit)](https://go.microsoft.com/fwlink/?LinkID=760868), either through the graphical software center if it's available, or through the command line with:

为基于 Debian/Ubuntu 的发行版安装 Visual Studio Code 的最简单方法是通过图形软件中心或通过命令行下载并安装[.deb包(64位)](https://go.microsoft.com/fwlink/?LinkID=760868)：

```bash
sudo apt install ./<file>.deb

# If you're on an older Linux distribution, you will need to run this instead:
# sudo dpkg -i <file>.deb
# sudo apt-get install -f # Install dependencies
```

Installing the .deb package will automatically install the apt repository and signing key to enable auto-updating using the system's package manager. Note that 32-bit and .tar.gz binaries are also available on the [download page](/Download).

安装 .deb 包将自动安装 apt 仓库，并签字，以便利用系统的软件包管理实现自我更新。请注意，32位和 .tar.gz 二进制文件也可以在[下载页面](/Download)上找到。

The repository and key can also be installed manually with the following script:

还可以使用以下脚本手动安装存储库和密钥：

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
```

Then update the package cache and install the package using:

然后更新包缓存并使用以下方法安装包：

```bash
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install code # or code-insiders
```

### RHEL, Fedora and CentOS based distributions (基于 RHEL、Fedora 和 Centos 的发行版)

We currently ship the stable 64-bit VS Code in a yum repository, the following script will install the key and repository:

我们目前在 yum 存储库中提供稳定的64位 VS Code，下面的脚本将安装密钥和存储库：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
```

Then update the package cache and install the package using `dnf` (Fedora 22 and above):

然后更新包缓存并使用 `dnf` (Fedora 22及更高版本)安装包：

```bash
dnf check-update
sudo dnf install code
```

Or on older versions using `yum`:

或者在旧版本上使用 `yum`：

```bash
yum check-update
sudo yum install code
```

Note that due to the manual signing process and the system we use to publish, the yum repo may lag behind and not get the latest version of VS Code immediately.

请注意，由于手动签名过程和我们用于发布的系统，yum repo 可能会落后，无法立即获得最新版本的 VS Code。

### openSUSE and SLE based distributions (基于 OpenSUSE 和 SLE 的发行版)

The yum repository above also works for openSUSE and SLE based systems, the following script will install the key and repository:

上面的 yum 存储库也适用于基于 openSUSE 和 SLE 的系统，下面的脚本将安装密钥和存储库：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/vscode.repo'
```

Then update the package cache and install the package using:

然后更新包缓存并使用以下方法安装包：

```bash
sudo zypper refresh
sudo zypper install code
```

### AUR package for Arch Linux (用于 Arch Linux 的 AUR 包)

There is a community maintained Arch User Repository (AUR) [package for VS Code](https://aur.archlinux.org/packages/visual-studio-code-bin).

有一个社区维护的 Arch 用户存储库 (AUR) [包作用于VS Code](https://aur.archlinux.org/packages/visual-studio-code-bin)。

To get more information about the installation from the AUR, please consult the following wiki entry:
[Install AUR Packages](https://wiki.archlinux.org/index.php/Arch_User_Repository#Build_and_install_the_package).

要从 AUR 获取有关安装的更多信息，请参考以下 wiki 条目：[Install AUR Packages](https://wiki.archlinux.org/index.php/Arch_User_Repository#Build_and_install_the_package)。

### Nix package for NixOS (or any Linux distribution using Nix package manager) (NixOS 下的 Nix 包(或任何 Linux 发行版的包管理器使用 Nix))

There is a community maintained [Nix package](https://github.com/NixOS/nixpkgs/blob/master/pkgs/applications/editors/vscode/default.nix) in the nixpkgs repository. In order to install it using Nix, set `allowUnfree` option to true in your `config.nix` and execute:

在 nixpkgs 存储库中有一个社区维护的 [Nix 包](https://github.com/NixOS/nixpkgs/blob/master/pkgs/applications/editors/vscode/default.nix)。要安装使用它，请在 `config.nix` 中将 `allowUnfree` 选项设置为 true，然后执行：

```bash
nix-env -i vscode
```

### Installing .rpm package manually (手动安装 .rpm 包)

The [.rpm package (64-bit)](https://go.microsoft.com/fwlink/?LinkID=760867) can also be manually downloaded and installed, however auto-updating won't work unless the repository above is installed. Once downloaded it can be installed using your package manager, for example with `dnf`:

[.rpm 包(64位)](https://go.microsoft.com/fwlink/?LinkID=760867)也可以手动下载和安装，但是除非安装了上述存储库，否则自动更新将无法工作。下载后，可以使用包管理器安装它，例如使用 `dnf`：

```bash
sudo dnf install <file>.rpm
```

Note that 32-bit and .tar.gz binaries are also available on the [download page](/Download).

请注意，32位和 .tar.gz 二进制文件也可以在[下载页面](/Download)上找到。

## Updates (更新)

VS Code ships monthly and you can see when a new release is available by checking [Updates](/updates). If the VS Code repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.

VS Code 每月发布一次，你可以通过检查更新来查看新版本何时可用。如果 VS Code 存储库安装正确，那么系统包管理器应该与系统上其他包相同的方式处理自动更新。

## Node.js

Node.js is a popular platform and runtime for easily building and running JavaScript applications. It also includes [npm](https://www.npmjs.com/), a Package Manager for Node.js modules. You'll see Node.js and npm mentioned frequently in our documentation and some optional VS Code tooling requires Node.js (for example, the VS Code [extension generator](/api/get-started/your-first-extension.md)).

Node.js 是一个流行的平台和流程，用于轻松编译和运行 JavaScript 应用程序。它还包括 [npm](https://www.npmjs.com/)，Node.js 模块的包管理器。你将在我们的文档中经常看到 Node.js 和 npm，一些可选的 VS Code 工具需要 Node.js (例如，VS Code [扩展生成器](/api/get-started/your-first-extension.md))。

If you'd like to install Node.js on Linux, see [Installing Node.js via package manager](https://nodejs.org/en/download/package-manager) to find the Node.js package and installation instructions tailored to your Linux distribution. You can also install and support multi version of Node.js by using the [Node Version Manager](https://github.com/creationix/nvm).

如果要在 Linux 上安装 Node.js，请参阅通过[包管理器安装 Node.js](https://nodejs.org/en/download/package-manager) ，以查找为 Linux 发行版量身定制的 Node.js 包和安装说明。你还可以使用[节点版本管理器](https://github.com/creationix/nvm)安装和支持 Node.js 的多版本。

To learn more about JavaScript and Node.js, see our [Node.js tutorial](/docs/nodejs/nodejs-tutorial.md), where you'll learn about running and debugging Node.js applications with VS Code.

要了解有关 JavaScript 和 Node.js 的更多信息，请参阅我们的 [Node.js 教程]，在这里你将了解如何使用 VS Code 运行和调试 Node.js 应用程序。

## Setting VS Code as the default text editor (将 VS Code 设置为默认文本编辑器)

### xdg-open

You can set the default text editor for text files (`text/plain`) that is used by `xdg-open` with the following command:

可以在文本文件 (`text/plain`) 下使用 `xdg-open` 命令，设置默认文本编辑器：

```bash
xdg-mime default code.desktop text/plain
```

### Debian alternatives system (Debian 替代系统)

Debian-based distributions allow setting a default *editor* using the [alternatives system](https://wiki.debian.org/DebianAlternatives), without concern for the MIME type. You can set this by running the following and selecting code:

Debian-based 的发行版允许使用[备选系统](https://wiki.debian.org/DebianAlternatives)设置默认*编辑器*，而不需要考虑 MIME 类型。您可以通过运行以下命令并选择代码来设置：

```bash
sudo update-alternatives --set editor /usr/bin/code
```

## Next steps

Once you have installed VS Code, these topics will help you learn more about it:

一旦安装了 VS Code，这些主题将帮助您了解有关它的更多信息：

* [Additional Components](/docs/setup/additional-components.md) - Learn how to install Git, Node.js, TypeScript and tools like Yeoman.
* [User Interface](/docs/getstarted/userinterface.md) - A quick orientation to VS Code.
* [User/Workspace Settings](/docs/getstarted/settings.md) - Learn how to configure VS Code to your preferences through settings.

* [Additional Components](/docs/setup/additional-components.md) - 了解如何安装 Git、Node.js、TypeScript 和类似于 Yeoman 的工具。
* [User Interface](/docs/getstarted/userinterface.md) - 对 VS Code 的快速定位。
* [User/Workspace Settings](/docs/getstarted/settings.md) - 了解如何通过设置将 VS Code 配置为你的首选项。

## Common questions (常见问题)

### Azure VM Issues (Azure VM 问题)

I'm getting a "Running without the SUID sandbox" error?

我遇到了一个 "Running without the SUID sandbox" 错误？

You can safely ignore this error.

你可以安全地忽略此错误。

### Debian and moving files to trash (将文件 Debian 并移动到垃圾桶)

If you see an error when deleting files from the VS Code Explorer on the Debian operating system, it might be because the trash implementation that VS Code is using is not there.

如果你在 Debian 操作系统上的 VS Code 资源管理器中删除文件时看到错误，这可能是因为 VS Code 使用的垃圾实现不在那里。

Run these commands to solve this issue:

运行以下命令来解决此问题：

```bash
sudo apt-get install gvfs-bin
```

### "Visual Studio Code is unable to watch for file changes in this large workspace" (error ENOSPC) ("Visual Studio Code 无法监视此大工作区中的文件更改"(error ENOSPC))

When you see this notification, it indicates that the VS Code file watcher is running out of handles because the workspace is large and contains many files. The current limit can be viewed by running:

当你看到此通知时，它表示 VS Code 文件监视程序的句柄不足，因为工作区很大，并且包含许多文件。

```bash
cat /proc/sys/fs/inotify/max_user_watches
```

The limit can be increased to its maximum by editing `/etc/sysctl.conf` and adding this line to the end of the file:

通过编辑 `/etc/sysctl.conf` 并将此行添加到文件结尾，可以将限制增加到最大值：

```bash
fs.inotify.max_user_watches=524288
```

The new value can then be loaded in by running `sudo sysctl -p`. Note that [Arch Linux](https://www.archlinux.org/) works a little differently, [view this page for advice](https://github.com/guard/listen/wiki/Increasing-the-amount-of-inotify-watchers).

然后可以通过运行 `sudo sysctl -p` 加载新值。请注意，[Arch Linux](https://www.archlinux.org/) 的工作方式有点不同，请[查看此页面以获取建议](https://github.com/guard/listen/wiki/Increasing-the-amount-of-inotify-watchers)。

While 524,288 is the maximum number of files that can be watched, if you're in an environment that is particularly memory constrained, you may wish to lower the number. Each file watch [takes up 540 bytes (32-bit) or ~1kB (64-bit)](https://stackoverflow.com/a/7091897/1156119), so assuming that all 524,288 watches are consumed, that results in an upper bound of around 256MB (32-bit) or 512MB (64-bit).

虽然 524,288 是可以监视的最大文件数，但如果你所在的环境特别受内存限制，你可能希望降低该数。每个文件监视[占用540字节(32位)或 ~1KB(64位)](https://stackoverflow.com/a/7091897/1156119)，因此假设所有 524,288 个监视都被占用，则会导致上界约为 256MB(32位)或 512MB(64位)。

Another option is to exclude specific workspace directories from the VS Code file watcher with the `files.watcherExclude` [setting](/docs/getstarted/settings.md). The default for `files.watcherExclude` excludes `node_modules` and some folders under `.git`, but you can add other directories that you don't want VS Code to track.

另一个选项是使用 `files.watcherExclude` [设置](/docs/getstarted/settings.md),从 VS Code 文件监视程序中排除特定的工作区目录。

```json
"files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/*/**": true
  }
```

### I can't see Chinese characters in Ubuntu (我在 Ubuntu 看不到汉字)

We're working on a fix. In the meantime, open the application menu, then choose **File** > **Preferences** > **Settings**. In the **Text Editor** > **Font** section, set "Font Family" to `Droid Sans Mono, Droid Sans Fallback`. If you'd rather edit the `settings.json` file directly, set `editor.fontFamily` as shown:

我们正在解决问题。同时，打开应用程序菜单，然后选择 **File** > **Preferences** > **Settings**。在 **Text Editor** > **Font** ，将"字体系列"设置为 `Droid Sans Mono, Droid Sans Fallback`。如果你想直接编辑 `settings.json` 文件，请设置 `editor.fontFamily`，如下所示：

```json
    "editor.fontFamily": "Droid Sans Mono, Droid Sans Fallback"
```

### Package git is not installed (未安装包 Git)

This error can appear during installation and is typically caused by the package manager's lists being out of date. Try updating them and installing again:

此错误可能在安装过程中出现，通常是由包管理器的列表过期造成的。尝试更新并重新安装：

```bash
# For .deb
sudo apt-get update

# For .rpm (Fedora 21 and below)
sudo yum update

# For .rpm (Fedora 22 and above)
sudo dnf update
```

### The code bin command does not bring the window to the foreground on Ubuntu (code bin 命令不会将窗口置于 Ubuntu 上的前台。)

Running `code .` on Ubuntu when VS Code is already open in the current directory will not bring VS Code into the foreground. This is a feature of the OS which can be disabled using `ccsm`.

当 VS Code 已经在当前目录中打开时，在 Ubuntu 上运行 `code .` 不会将 VS Code 带到前台。这是操作系统的一个功能，可以使用 `ccsm` 禁用。

```bash
# Install
sudo apt-get update
sudo apt-get install compizconfig-settings-manager

# Run
ccsm
```

Under **General** > **General Options** > **Focus & Raise Behaviour**, set "Focus Prevention Level" to "Off". Remember this is an OS-level setting that will apply to all applications, not just VS Code.

在 **General** > **General Options** > **Focus & Raise Behaviour** 下，将 "Focus Prevention Level" 设置为 "Off"。记住，这是一个操作系统级别的设置，将应用于所有应用程序，而不仅仅是 VS Code。

### Cannot install .deb package due to "/etc/apt/sources.list.d/vscode.list: No such file or directory" (无法安装 .deb 包，原因是"/etc/apt/sources.list.d/vscode.list:没有此类文件或目录")

This can happen when `sources.list.d` doesn't exist or you don't have access to create the file. To fix this, try manually creating the folder and an empty `vscode.list` file:

当 `sources.list.d` 不存在或你没有创建文件的权限时，可能会发生这种情况。要解决此问题，请尝试手动创建文件夹和空的 `vscode.list` 文件：

```bash
sudo mkdir /etc/apt/sources.list.d
sudo touch /etc/apt/sources.list.d/vscode.list
```

### Cannot move or resize the window while X forwarding a remote window (X 转发远程窗口时无法移动或调整窗口大小)

If you are using X forwarding to use VS Code remotely, you will need to use the native title bar to ensure you can properly manipulate the window. You can switch to using it by setting `window.titleBarStyle` to `native`.

如果在 VS Code 上使用 X 转发远程，则需要使用本机标题栏以确保可以正确操作窗口。通过将 `window.titleBarStyle` 设置为 `native`，来使用它。

### Using the custom title bar (使用自定义标题栏)

The custom title bar and menus were enabled by default on Linux for several months. The custom title bar has been a success on Windows, but the customer response on Linux suggests otherwise. Based on feedback, we have decided to make this setting opt-in on Linux and leave the native title bar as the default.

The custom title bar provides many benefits including great theming support and better accessibility through keyboard navigation and screen readers. Unfortunately, these benefits do not translate as well to the Linux platform. Linux has a variety of desktop environments and window managers that can make the VS Code theming look foreign to users. For users needing the accessibility improvements, we recommend enabling the custom title bar when running in accessibility mode using a screen reader. You can still manually set the title bar with the **Window: Title Bar Style** (`window.titleBarStyle`) setting.

### Broken cursor in editor with display scaling enabled

Due to an upstream [issue](https://github.com/electron/electron/issues/14787) with Electron, the mouse cursor may render incorrectly with scaling enabled. If you notice that the usual text cursor is not being rendered inside the editor as you would expect, try falling back to the native menu bar by configuring the setting `window.titleBarStyle` to `native`.

### Repository changed its origin value

If you receive an error similar to the following:

```
E: Repository '...' changed its 'Origin' value from '...' to '...'
N: This must be accepted explicitly before updates for this repository can be applied. See apt-secure(8) manpage for details.
```

Use `apt` instead of `apt-get` and you will be prompted to accept the origin change:

```bash
sudo apt update
```
