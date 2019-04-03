---
# DO NOT TOUCH — Managed by doc writer
# 请勿更改-这个文档由作者管理
ContentId: 37b6ae0a-d1b5-48b6-9bd4-9b50ef11d573
DateApproved: 3/7/2019
批准日期：3/7/2019
# Summarize the whole topic in less than 300 characters for SEO purpose
# 为达到搜索引擎优化（SEO）的目的，用300个以内字符总结整个主题
MetaDescription: Learn how to add custom themes for colors and icons in Visual Studio Code.
MetaDescription: 了解如何在Visual Studio Code中为颜色和图标添加自定义主题。
---

# Theming

# 主题

In Visual Studio Code, there are two types of themes:

在 Visual Studio Code 中，有两种类型的主题：

- **Color Theme**: A mapping from both UI Component Identifier and Text Token Identifier to colors. Color theme allows you to apply your favorite colors to both VS Code UI Components and the text in the editor.
- **颜色主題**: 从 UI 组件识别码和文本标记识别码到颜色的映射。颜色主题允许你将自己喜欢的颜色应用于 VS Code UI 组件和编辑器中的文本。

- **Icon Theme**: A mapping from file type / file name to images. The file icon is displayed across the VS Code UI in places such as File Explorer, Quick Open List, and Editor Tab.
- **图标主题**: 从文件类型/文件名到图像的映射。文件图标显示在 VS Code UI 中的文件资源管理器、快速打开列表和编辑器选项卡等位置。

## Color Theme

## 颜色主题

![color-theme](images/theming/color-theme.png)
！[颜色-主题]（图像/主题/颜色-主题.png）
As you can see in the illustration, Color Theme defines two mappings:
如图所示，颜色主题定义了两个映射:

- The `colors` mapping that controls colors for UI Components.
- `颜色`映射管理 UI 组件的颜色。
- The `tokenColors` mapping that controls colors for each source code token (your source code is broken into tokens by a [grammar](/api/language-extensions/syntax-highlight-guide)).
- `标记颜色`映射管理每个源代码标记的颜色(你的源代码被[语法]分解为标记(/api/language-extensions/syntax-highlight-guide))。

We have a [Color Theme Guide](/api/extension-guides/color-theme) and a [Color Theme Sample](https://github.com/Microsoft/vscode-extension-samples/tree/master/theme-sample) that illustrates how to create a theme.
我们有一个[颜色主题指南](/api/extension-guides/Color-Theme)和一个[颜色主题样本](https://github.com/microsoft/vsco-extension-samples/tree/master/theme-Sample)演示如何创建主题。

## Icon Theme

## 图标主题

Icon themes allow you to:
图标主题允许你：

- Create a mapping from unique icon identifiers to images or font icons.
- 创建从独特图标识别码到图像或字体图标的映射。

- Associate files to these unique icon identifiers by filenames or file language types.
- 根据文件名或文件语言类型将文件关联到独特图标识别码。

The [Icon Theme Guide](/api/extension-guides/icon-theme) discusses how to create an Icon Theme.
[图标主题指南](/api/extension-guides/icon-theme)讨论如何创建图标主题。

![icon-theme](images/theming/icon-theme.png)
[图标-主题](images/theming/icon-theme.png)
