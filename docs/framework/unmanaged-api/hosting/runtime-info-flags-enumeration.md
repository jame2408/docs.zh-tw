---
title: "RUNTIME_INFO_FLAGS 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 697111efbb4e3f705c881ec677f781b6e3e6959d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="b30a2-102">RUNTIME_INFO_FLAGS 列舉</span><span class="sxs-lookup"><span data-stu-id="b30a2-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="b30a2-103">包含值，指出應該傳回 common language runtime (CLR) 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b30a2-104">語法</span><span class="sxs-lookup"><span data-stu-id="b30a2-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b30a2-105">成員</span><span class="sxs-lookup"><span data-stu-id="b30a2-105">Members</span></span>  
  
|<span data-ttu-id="b30a2-106">成員</span><span class="sxs-lookup"><span data-stu-id="b30a2-106">Member</span></span>|<span data-ttu-id="b30a2-107">說明</span><span class="sxs-lookup"><span data-stu-id="b30a2-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="b30a2-108">指出不應該包含目錄資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="b30a2-109">指出不應該包含版本資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="b30a2-110">表示不應該在發生錯誤時顯示錯誤對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="b30a2-111">表示呼叫的效果[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 旗標的函式應該覆寫。</span><span class="sxs-lookup"><span data-stu-id="b30a2-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="b30a2-112">也就是在發生錯誤，而不是要隱藏應該會顯示 [安裝] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="b30a2-113">表示要求的執行階段的 AMD 64 相容版本的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="b30a2-114">表示要求的執行階段 IA 64 相容版本的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="b30a2-115">表示要求的執行階段與 x86 相容的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="b30a2-116">表示應該包含版本升級的資訊。</span><span class="sxs-lookup"><span data-stu-id="b30a2-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b30a2-117">備註</span><span class="sxs-lookup"><span data-stu-id="b30a2-117">Remarks</span></span>  
 <span data-ttu-id="b30a2-118">下列平台架構旗標可以一次只能指定的一個，而且無法結合：</span><span class="sxs-lookup"><span data-stu-id="b30a2-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="b30a2-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="b30a2-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="b30a2-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="b30a2-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="b30a2-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="b30a2-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b30a2-122">需求</span><span class="sxs-lookup"><span data-stu-id="b30a2-122">Requirements</span></span>  
 <span data-ttu-id="b30a2-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b30a2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b30a2-124">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b30a2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b30a2-125">**程式庫：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b30a2-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b30a2-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b30a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30a2-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b30a2-127">See Also</span></span>  
 [<span data-ttu-id="b30a2-128">裝載列舉</span><span class="sxs-lookup"><span data-stu-id="b30a2-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)