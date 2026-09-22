# GIT-ADD-FOLDER

[ENGLISH](README.md) | [中文](README.cn.md)

通过 Windows 文件资源管理器的右键菜单，一键添加 Git 仓库中的所有变更。

安装 `git-add.reg` 后，右键菜单中会新增 **Git Add All** 项。使用该功能时，会打开一个控制台窗口，进入你所选择的文件夹，并运行：

```text
git add .
```

当你需要一次暂存多个文件，而不是逐个添加文件时，这个工具会很方便。对于不想暂存的文件，仍然可以使用 Git 的常规忽略和暂存流程进行排除。

## 使用要求

- 仅支持 Windows
- Windows 系统中必须已经安装 Git for Windows
- 选择的文件夹应当是 Git 仓库，或位于某个 Git 仓库中

## 安装

1. 下载或克隆本仓库。
2. 双击 `git-add.reg`。
3. 确认 Windows 注册表编辑器的提示。
4. 如果 **Git Add All** 没有立即出现，请重新启动文件资源管理器。

注册表文件使用 Git for Windows 的默认图标路径。如果 Git 安装在其他位置，菜单项仍然可以正常工作，但图标可能不会显示。

## 使用方法

1. 打开文件资源管理器，找到你的 Git 仓库。
2. 可以使用以下任一方法：
	- 右键单击仓库文件夹，然后选择 **Git Add All**。
	- 打开仓库文件夹，在空白处右键单击，然后选择 **Git Add All**。

![Git Add All 右键菜单项](image/p01.jpg)

3. 控制台窗口会在该文件夹中运行 `git add .`。
4. 使用 `git status` 检查已暂存的文件，然后在确认无误后提交。

该命令会暂存所选文件夹下的文件。它不会创建提交，也不会向远程仓库推送任何内容。

## 卸载

最简单的卸载方法是双击 `git-add-uninstall.reg`，然后确认 Windows 注册表编辑器的提示。如果 **Git Add All** 仍然显示，请重新启动文件资源管理器。

也可以打开注册表编辑器，手动删除以下注册表项：

```text
HKEY_CLASSES_ROOT\Directory\Background\shell\GitAdd
HKEY_CLASSES_ROOT\Directory\shell\GitAdd
```

只有在确定要卸载此工具时，才删除这些注册表项。
