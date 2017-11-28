---
title: "CoreClrDebugRuntimeInfo 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugRuntimeInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e18416822aed6020fb0de8eb5bc7d38e4cd2eb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="1d20b-102">CoreClrDebugRuntimeInfo 結構</span><span class="sxs-lookup"><span data-stu-id="1d20b-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="1d20b-103">代表載入遠端電腦上之處理序的 Common Language Runtime (CLR) 執行個體。</span><span class="sxs-lookup"><span data-stu-id="1d20b-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d20b-104">語法</span><span class="sxs-lookup"><span data-stu-id="1d20b-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="1d20b-105">成員</span><span class="sxs-lookup"><span data-stu-id="1d20b-105">Members</span></span>  
  
|<span data-ttu-id="1d20b-106">成員</span><span class="sxs-lookup"><span data-stu-id="1d20b-106">Member</span></span>|<span data-ttu-id="1d20b-107">說明</span><span class="sxs-lookup"><span data-stu-id="1d20b-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="1d20b-108">在目標電腦上執行之遠端偵錯 Proxy 所指派的執行階段識別項。</span><span class="sxs-lookup"><span data-stu-id="1d20b-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d20b-109">需求</span><span class="sxs-lookup"><span data-stu-id="1d20b-109">Requirements</span></span>  
 <span data-ttu-id="1d20b-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d20b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d20b-111">**標頭：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="1d20b-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="1d20b-112">**程式庫：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="1d20b-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="1d20b-113">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1d20b-113">**.NET Framework Versions:** 3.5 SP1</span></span>