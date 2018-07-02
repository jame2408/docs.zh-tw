---
title: dotnet tool list 命令 - .NET Core CLI
description: dotnet tool list 命令會列出您電腦中指定的 .NET Core 通用工具。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 5f4793cd37c3a8df06eb6930ad9f381ac70d4e67
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696721"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="5efb9-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="5efb9-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="5efb9-104">名稱</span><span class="sxs-lookup"><span data-stu-id="5efb9-104">Name</span></span>

<span data-ttu-id="5efb9-105">`dotnet tool list` - 列出您電腦上的預設目錄或指定路徑中目前安裝的所有 [.NET Core 通用工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5efb9-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5efb9-106">概要</span><span class="sxs-lookup"><span data-stu-id="5efb9-106">Synopsis</span></span>

```
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="5efb9-107">描述</span><span class="sxs-lookup"><span data-stu-id="5efb9-107">Description</span></span>

<span data-ttu-id="5efb9-108">`dotnet tool list` 命令可讓您列出電腦上所有使用者 (目前的使用者設定檔)，或指定路徑中安裝的所有 .NET Core 通用工具。</span><span class="sxs-lookup"><span data-stu-id="5efb9-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="5efb9-109">此命令會列出套件名稱、安裝的版本和通用工具命令。</span><span class="sxs-lookup"><span data-stu-id="5efb9-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="5efb9-110">若要使用這個 list 命令，您必須使用 `--global` 選項指定您要查看所有使用者範圍工具，或使用 `--tool-path` 選項指定自訂路徑。</span><span class="sxs-lookup"><span data-stu-id="5efb9-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="5efb9-111">選項</span><span class="sxs-lookup"><span data-stu-id="5efb9-111">Options</span></span>

`-g|--global`

<span data-ttu-id="5efb9-112">列出使用者範圍通用工具。</span><span class="sxs-lookup"><span data-stu-id="5efb9-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="5efb9-113">無法與 `--tool-path` 選項合併使用。</span><span class="sxs-lookup"><span data-stu-id="5efb9-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="5efb9-114">如果未指定此選項，您必須指定 `--tool-path` 選項。</span><span class="sxs-lookup"><span data-stu-id="5efb9-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="5efb9-115">印出命令的簡短說明。</span><span class="sxs-lookup"><span data-stu-id="5efb9-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="5efb9-116">指定用來尋找通用工具的自訂位置。</span><span class="sxs-lookup"><span data-stu-id="5efb9-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="5efb9-117">PATH 可為絕對路徑或相對路徑。</span><span class="sxs-lookup"><span data-stu-id="5efb9-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="5efb9-118">無法與 `--global` 選項合併使用。</span><span class="sxs-lookup"><span data-stu-id="5efb9-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="5efb9-119">如果未指定此選項，您必須指定 `--global` 選項。</span><span class="sxs-lookup"><span data-stu-id="5efb9-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="5efb9-120">範例</span><span class="sxs-lookup"><span data-stu-id="5efb9-120">Examples</span></span>

<span data-ttu-id="5efb9-121">列出您電腦上所有使用者 (目前的使用者設定檔) 安裝的所有通用工具使用者：</span><span class="sxs-lookup"><span data-stu-id="5efb9-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="5efb9-122">列出特定 Windows 資料夾中的通用工具：</span><span class="sxs-lookup"><span data-stu-id="5efb9-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="5efb9-123">列出特定 Linux/macOS 資料夾中的通用工具：</span><span class="sxs-lookup"><span data-stu-id="5efb9-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="5efb9-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5efb9-124">See also</span></span>

[<span data-ttu-id="5efb9-125">.NET Core 通用工具</span><span class="sxs-lookup"><span data-stu-id="5efb9-125">.NET Core Global Tools</span></span>](global-tools.md)