---
title: "開始使用 Azure 檔案儲存體使用 F #"
description: "搭配 Azure 檔案儲存在雲端中儲存檔案資料，而且從 Azure 虛擬機器 (VM) 掛接您雲端的檔案共用或從內部部署應用程式執行 Windows。"
keywords: "visual f #、 f #，功能性程式設計，.NET 中，.NET Core，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 66b2503744e9024deac3d6dabea57da4fd393bd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="401ca-104">開始使用 Azure 檔案儲存體使用 F #</span><span class="sxs-lookup"><span data-stu-id="401ca-104">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="401ca-105">Azure 檔案儲存體是一項服務，提供在雲端中使用標準的檔案共用[伺服器訊息區塊 (SMB) 通訊協定](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)。</span><span class="sxs-lookup"><span data-stu-id="401ca-105">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="401ca-106">支援 SMB 2.1 和 SMB 3.0。</span><span class="sxs-lookup"><span data-stu-id="401ca-106">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="401ca-107">使用 Azure 檔案儲存體，您可以移轉快速且昂貴的撰寫不依賴至 Azure 的檔案共用的舊版應用程式。</span><span class="sxs-lookup"><span data-stu-id="401ca-107">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="401ca-108">在 Azure 虛擬機器或雲端服務，或從內部部署用戶端執行的應用程式可以掛接在雲端中，將檔案共用，就像桌面應用程式裝載在典型的 SMB 共用。</span><span class="sxs-lookup"><span data-stu-id="401ca-108">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="401ca-109">任何數目的應用程式元件即可掛接或同時存取的儲存體檔案共用。</span><span class="sxs-lookup"><span data-stu-id="401ca-109">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="401ca-110">檔案儲存體概念的概觀，請參閱[檔案存放裝置的.NET 指南](/azure/storage/storage-dotnet-how-to-use-files)。</span><span class="sxs-lookup"><span data-stu-id="401ca-110">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="401ca-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="401ca-111">Prerequisites</span></span>

<span data-ttu-id="401ca-112">若要使用本指南，您必須先[建立 Azure 儲存體帳戶](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="401ca-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="401ca-113">您還需要此帳戶的儲存體存取金鑰。</span><span class="sxs-lookup"><span data-stu-id="401ca-113">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="401ca-114">建立 F # 指令碼，並開始 F # Interactive</span><span class="sxs-lookup"><span data-stu-id="401ca-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="401ca-115">這篇文章中的範例可以用於 F # 應用程式或 F # 指令碼。</span><span class="sxs-lookup"><span data-stu-id="401ca-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="401ca-116">若要建立 F # 指令碼，建立檔案之`.fsx`擴充功能，例如`files.fsx`，F # 開發環境中。</span><span class="sxs-lookup"><span data-stu-id="401ca-116">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="401ca-117">接下來，使用[封裝管理員](package-management.md)例如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安裝`WindowsAzure.Storage`封裝和參考`WindowsAzure.Storage.dll`指令碼使用`#r`指示詞。</span><span class="sxs-lookup"><span data-stu-id="401ca-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="401ca-118">加入命名空間宣告</span><span class="sxs-lookup"><span data-stu-id="401ca-118">Add namespace declarations</span></span>

<span data-ttu-id="401ca-119">加入下列`open`上方的陳述式`files.fsx`檔案：</span><span class="sxs-lookup"><span data-stu-id="401ca-119">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="401ca-120">取得連接字串</span><span class="sxs-lookup"><span data-stu-id="401ca-120">Get your connection string</span></span>

<span data-ttu-id="401ca-121">此教學課程中，您將需要 Azure 儲存體連接字串。</span><span class="sxs-lookup"><span data-stu-id="401ca-121">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="401ca-122">如需連接字串的詳細資訊，請參閱[設定儲存體連接字串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="401ca-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="401ca-123">教學課程中，您會輸入您的連接字串中指令碼中，像這樣：</span><span class="sxs-lookup"><span data-stu-id="401ca-123">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="401ca-124">不過，這是**不建議**用於真實的專案。</span><span class="sxs-lookup"><span data-stu-id="401ca-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="401ca-125">儲存體帳戶金鑰是類似於儲存體帳戶的根密碼。</span><span class="sxs-lookup"><span data-stu-id="401ca-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="401ca-126">一律為保護您的儲存體帳戶金鑰，請小心。</span><span class="sxs-lookup"><span data-stu-id="401ca-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="401ca-127">避免將其散發給其他使用者，硬式編碼，或將它儲存在其他人可以存取純文字檔案。</span><span class="sxs-lookup"><span data-stu-id="401ca-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="401ca-128">您可以重新產生您使用 Azure 入口網站，如果您認為可能已受到危害的金鑰。</span><span class="sxs-lookup"><span data-stu-id="401ca-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="401ca-129">用於真實的應用程式，以維護您的儲存體連接字串的最佳方式是在組態檔中。</span><span class="sxs-lookup"><span data-stu-id="401ca-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="401ca-130">若要從組態檔擷取連接字串，您可以：</span><span class="sxs-lookup"><span data-stu-id="401ca-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="401ca-131">使用 Azure 組態管理員是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="401ca-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="401ca-132">您也可以使用例如.NET Framework API`ConfigurationManager`型別。</span><span class="sxs-lookup"><span data-stu-id="401ca-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="401ca-133">剖析連接字串</span><span class="sxs-lookup"><span data-stu-id="401ca-133">Parse the connection string</span></span>

<span data-ttu-id="401ca-134">若要剖析的連接字串，使用：</span><span class="sxs-lookup"><span data-stu-id="401ca-134">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="401ca-135">這會傳回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="401ca-135">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="401ca-136">建立檔案服務用戶端</span><span class="sxs-lookup"><span data-stu-id="401ca-136">Create the File service client</span></span>

<span data-ttu-id="401ca-137">`CloudFileClient`類型可讓您以程式設計方式使用檔案儲存體中儲存的檔案。</span><span class="sxs-lookup"><span data-stu-id="401ca-137">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="401ca-138">以下是如何建立服務用戶端：</span><span class="sxs-lookup"><span data-stu-id="401ca-138">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="401ca-139">現在您已準備好要寫入的資料來讀取和寫入資料檔案儲存體的程式碼。</span><span class="sxs-lookup"><span data-stu-id="401ca-139">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="401ca-140">建立檔案共用</span><span class="sxs-lookup"><span data-stu-id="401ca-140">Create a file share</span></span>

<span data-ttu-id="401ca-141">這個範例示範如何建立檔案共用，如果不存在：</span><span class="sxs-lookup"><span data-stu-id="401ca-141">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="401ca-142">建立根目錄和子目錄</span><span class="sxs-lookup"><span data-stu-id="401ca-142">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="401ca-143">這裡，您會取得目錄的根目錄，並取得根目錄的子目錄。</span><span class="sxs-lookup"><span data-stu-id="401ca-143">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="401ca-144">您建立這兩者如果它們不存在。</span><span class="sxs-lookup"><span data-stu-id="401ca-144">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="401ca-145">將文字上傳檔案</span><span class="sxs-lookup"><span data-stu-id="401ca-145">Upload text as a file</span></span>

<span data-ttu-id="401ca-146">這個範例示範如何將文字當做檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="401ca-146">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="401ca-147">將檔案下載至本機檔案的複本</span><span class="sxs-lookup"><span data-stu-id="401ca-147">Download a file to a local copy of the file</span></span>

<span data-ttu-id="401ca-148">這裡您下載剛才建立的檔案附加到本機檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="401ca-148">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="401ca-149">設定檔案共用的大小上限</span><span class="sxs-lookup"><span data-stu-id="401ca-149">Set the maximum size for a file share</span></span>

<span data-ttu-id="401ca-150">下列範例會示範如何檢查共用資源的目前使用量以及如何設定共用的配額。</span><span class="sxs-lookup"><span data-stu-id="401ca-150">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="401ca-151">`FetchAttributes`必須先呼叫填入共用`Properties`，和`SetProperties`將本機變更傳播至 Azure 檔案儲存體。</span><span class="sxs-lookup"><span data-stu-id="401ca-151">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="401ca-152">產生的檔案或檔案共用的共用的存取簽章</span><span class="sxs-lookup"><span data-stu-id="401ca-152">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="401ca-153">您可以產生共用的存取簽章 (SAS) 的檔案共用，或針對個別檔案。</span><span class="sxs-lookup"><span data-stu-id="401ca-153">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="401ca-154">您也可以建立共用的存取原則來管理共用的存取簽章的檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="401ca-154">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="401ca-155">建立共用的存取原則被建議，因為它提供撤銷 SAS，如果它應該會受到危害的方法。</span><span class="sxs-lookup"><span data-stu-id="401ca-155">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="401ca-156">在這裡，您建立共用存取原則共用上，，然後使用該原則的條件約束提供共用中的檔案上的 SAS。</span><span class="sxs-lookup"><span data-stu-id="401ca-156">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="401ca-157">如需有關建立和使用共用的存取簽章的詳細資訊，請參閱[使用共用存取簽章 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1)和[建立並使用 SAS，以使用 Blob 儲存體](/azure/storage/storage-dotnet-shared-access-signature-part-2)。</span><span class="sxs-lookup"><span data-stu-id="401ca-157">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="401ca-158">將檔案複製</span><span class="sxs-lookup"><span data-stu-id="401ca-158">Copy files</span></span>

<span data-ttu-id="401ca-159">您可以將檔案複製到另一個檔案或 blob 或 blob 檔案。</span><span class="sxs-lookup"><span data-stu-id="401ca-159">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="401ca-160">如果您將 blob 複製到檔案或檔案的 blob，您*必須*使用共用的存取簽章 (SAS) 驗證來源物件，即使您要複製之相同的儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="401ca-160">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="401ca-161">將檔案複製到另一個檔案</span><span class="sxs-lookup"><span data-stu-id="401ca-161">Copy a file to another file</span></span>

<span data-ttu-id="401ca-162">在這裡，您將檔案複製到相同的共用中的另一個檔案。</span><span class="sxs-lookup"><span data-stu-id="401ca-162">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="401ca-163">因為相同的儲存體帳戶中的檔案之間，複製此複製操作，您可以使用共用金鑰驗證來進行複製。</span><span class="sxs-lookup"><span data-stu-id="401ca-163">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="401ca-164">將檔案複製到 blob</span><span class="sxs-lookup"><span data-stu-id="401ca-164">Copy a file to a blob</span></span>

<span data-ttu-id="401ca-165">在這裡，您可以建立檔案並將它複製到相同的儲存體帳戶內的 blob。</span><span class="sxs-lookup"><span data-stu-id="401ca-165">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="401ca-166">您建立 SAS，使原始程式檔，以便讓服務使用在複製作業期間驗證來源檔案的存取權。</span><span class="sxs-lookup"><span data-stu-id="401ca-166">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="401ca-167">您可以將 blob 複製檔案相同的方式。</span><span class="sxs-lookup"><span data-stu-id="401ca-167">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="401ca-168">如果來源物件是 blob，然後建立複製作業期間驗證存取該 blob 的 SAS。</span><span class="sxs-lookup"><span data-stu-id="401ca-168">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="401ca-169">疑難排解檔案存放裝置使用度量</span><span class="sxs-lookup"><span data-stu-id="401ca-169">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="401ca-170">Azure 儲存體分析度量資訊支援檔案存放裝置。</span><span class="sxs-lookup"><span data-stu-id="401ca-170">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="401ca-171">度量資料，您可以追蹤要求，以及診斷問題。</span><span class="sxs-lookup"><span data-stu-id="401ca-171">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="401ca-172">您可以啟用 從檔案儲存體度量[Azure 入口網站](https://portal.azure.com)，或您可以從 F # 中執行它，像這樣：</span><span class="sxs-lookup"><span data-stu-id="401ca-172">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="401ca-173">後續步驟</span><span class="sxs-lookup"><span data-stu-id="401ca-173">Next steps</span></span>

<span data-ttu-id="401ca-174">請參閱下列連結取得 Azure 檔案儲存體的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="401ca-174">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="401ca-175">概念性文章和影片</span><span class="sxs-lookup"><span data-stu-id="401ca-175">Conceptual articles and videos</span></span>

- [<span data-ttu-id="401ca-176">Azure 檔案儲存體： 格局的無耗損雲端 SMB 檔案系統的 Windows 和 Linux</span><span class="sxs-lookup"><span data-stu-id="401ca-176">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="401ca-177">如何使用 Linux 的 Azure 檔案儲存體</span><span class="sxs-lookup"><span data-stu-id="401ca-177">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="401ca-178">工具檔案存放裝置的支援</span><span class="sxs-lookup"><span data-stu-id="401ca-178">Tooling support for File storage</span></span>

- [<span data-ttu-id="401ca-179">使用 Azure 儲存體的 Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="401ca-179">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="401ca-180">如何使用 Microsoft Azure 儲存體的 AzCopy</span><span class="sxs-lookup"><span data-stu-id="401ca-180">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="401ca-181">使用 Azure CLI 搭配 Azure 儲存體</span><span class="sxs-lookup"><span data-stu-id="401ca-181">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="401ca-182">參考資料</span><span class="sxs-lookup"><span data-stu-id="401ca-182">Reference</span></span>

- [<span data-ttu-id="401ca-183">儲存體用戶端程式庫.NET 參考</span><span class="sxs-lookup"><span data-stu-id="401ca-183">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="401ca-184">檔案服務 REST API 參考</span><span class="sxs-lookup"><span data-stu-id="401ca-184">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="401ca-185">部落格文章</span><span class="sxs-lookup"><span data-stu-id="401ca-185">Blog posts</span></span>

- [<span data-ttu-id="401ca-186">Azure 檔案儲存體已上市</span><span class="sxs-lookup"><span data-stu-id="401ca-186">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="401ca-187">在 Azure 檔案儲存體</span><span class="sxs-lookup"><span data-stu-id="401ca-187">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="401ca-188">介紹 Microsoft Azure 檔案服務</span><span class="sxs-lookup"><span data-stu-id="401ca-188">Introducing Microsoft Azure File Service</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [<span data-ttu-id="401ca-189">Microsoft Azure 檔案的持續連線</span><span class="sxs-lookup"><span data-stu-id="401ca-189">Persisting connections to Microsoft Azure Files</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)