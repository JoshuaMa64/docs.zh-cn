---
title: "dotnet 命令 - .NET Core CLI"
description: "了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。"
keywords: "dotnet, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f377ea55278ae382f56a0dc0cbcf1bb99f49eca
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-command"></a>dotnet 命令

## <a name="name"></a>名称

`dotnet` - 运行命令行命令的通用驱动程序。

## <a name="synopsis"></a>摘要

`dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose] [--fx-version] [--additionalprobingpath] [-h|--help]`

## <a name="description"></a>描述

`dotnet` 是用于命令行接口 (CLI) 工具链的通用驱动程序。 它可自行调用，并提供简短的使用说明。

每种特定功能均实现为命令。 若要使用此功能，请在 `dotnet` 后指定该命令，例如 [`dotnet build`](dotnet-build.md)。 该命令后的所有参数均为其自有参数。

`dotnet` 自行作为命令使用的唯一情况是运行[依赖于框架的应用](../deploying/index.md)。 在 `dotnet` 谓词后指定应用程序 DLL 便可执行该应用程序（例如，`dotnet myapp.dll`）。

## <a name="options"></a>选项

`-v|--verbose`

启用详细输出。

`-d|--diagnostics`

启用诊断输出。

`--fx-version <VERSION>`

运行应用程序所使用的已安装共享框架的版本。

`--additionalprobingpath <PATH>`

包含要进行探测的探测策略和程序集的路径。

`--version`

打印出 CLI 工具的版本。

`--info`

打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。

`-h|--help`

打印出有关命令的简短帮助。 如果使用 `dotnet`，还会打印可用命令的列表。

## <a name="dotnet-commands"></a>dotnet 命令

### <a name="general"></a>常规

命令 | 函数
--- | ---
[dotnet-build](dotnet-build.md) | 生成 .NET Core 应用程序。
[dotnet-clean](dotnet-clean.md) | 清理生成输出。
[dotnet-migrate](dotnet-migrate.md) | 将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。
[dotnet-msbuild](dotnet-msbuild.md) | 提供对 MSBuild 命令行的访问权限。
[dotnet-new](dotnet-new.md) | 为给定的模板初始化 C# 或 F # 项目。
[dotnet-pack](dotnet-pack.md) | 创建代码的 NuGet 包。
[dotnet-publish](dotnet-publish.md) | 发布 .NET 依赖于框架或独立应用程序。
[dotnet-restore](dotnet-restore.md) | 还原给定应用程序的依赖项。
[dotnet-run](dotnet-run.md) | 从源运行应用程序。
[dotnet-sln](dotnet-sln.md) | 用于添加、删除和列出解决方案文件中项目的选项。
[dotnet-test](dotnet-test.md) | 使用测试运行程序运行测试。

### <a name="project-references"></a>项目引用

命令 | 函数
--- | ---
[dotnet-add 引用](dotnet-add-reference.md) | 添加项目引用。
[dotnet-list 引用](dotnet-list-reference.md) | 列出项目引用。
[dotnet-remove 引用](dotnet-remove-reference.md) | 删除项目引用。

### <a name="nuget-packages"></a>NuGet 包

命令 | 函数
--- | ---
[dotnet-add 包](dotnet-add-package.md) | 添加 NuGet 包。
[dotnet-remove 包](dotnet-remove-package.md) | 删除 NuGet 包。

### <a name="nuget-commands"></a>NuGet 命令

命令 | 函数
--- | ---
[dotnet-nuget delete](dotnet-nuget-delete.md) | 从服务器删除或取消列出包。
[dotnet-nuget locals](dotnet-nuget-locals.md) | 清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。
[dotnet-nuget push](dotnet-nuget-push.md) | 将包推送到服务器，并将其发布。

## <a name="examples"></a>示例

初始化可以编译和运行的示例 .NET Core 控制台应用程序：

`dotnet new console`

还原给定应用程序的依赖项：

`dotnet restore`

生成给定目录中的项目及其依赖项：

`dotnet build`

运行名为 `myapp.dll` 的依赖于框架的应用：

`dotnet myapp.dll`

## <a name="environment-variables"></a>环境变量

`DOTNET_PACKAGES`

主包缓存。 如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。

`DOTNET_SERVICING`

指定加载运行时期间共享主机要使用的服务索引的位置。

`DOTNET_CLI_TELEMETRY_OPTOUT`

指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。 设置为 `true` 以选择退出遥测功能（接受值 `true`、`1` 或 `yes`）；否则，设置为 `false` 以选择加入遥测功能（接受值 `false`、`0` 或 `no`）。 如果未设置，则默认为 `false` 且遥测功能为活动状态。

