---
title: "EBindPolicyLevels 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e55fdb58129cd530bb63f26fab0be471b133d62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="efce5-102">EBindPolicyLevels 列舉</span><span class="sxs-lookup"><span data-stu-id="efce5-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="efce5-103">請提供旗標，以指定的層級套用或修改組件的原則。</span><span class="sxs-lookup"><span data-stu-id="efce5-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efce5-104">語法</span><span class="sxs-lookup"><span data-stu-id="efce5-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="efce5-105">成員</span><span class="sxs-lookup"><span data-stu-id="efce5-105">Members</span></span>  
  
|<span data-ttu-id="efce5-106">成員</span><span class="sxs-lookup"><span data-stu-id="efce5-106">Member</span></span>|<span data-ttu-id="efce5-107">說明</span><span class="sxs-lookup"><span data-stu-id="efce5-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="efce5-108">指定原則應該套用系統管理員層級。</span><span class="sxs-lookup"><span data-stu-id="efce5-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="efce5-109">指定原則應該套用應用程式層級。</span><span class="sxs-lookup"><span data-stu-id="efce5-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="efce5-110">指定原則應該套用主機層級。</span><span class="sxs-lookup"><span data-stu-id="efce5-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="efce5-111">不指定原則層級旗標。</span><span class="sxs-lookup"><span data-stu-id="efce5-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="efce5-112">指定原則應該 publisher 層級套用。</span><span class="sxs-lookup"><span data-stu-id="efce5-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="efce5-113">指定原則應該適用變數層級。</span><span class="sxs-lookup"><span data-stu-id="efce5-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="efce5-114">指定原則應該支援.NET Framework 組件實作之間的可攜性。</span><span class="sxs-lookup"><span data-stu-id="efce5-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="efce5-115">請參閱[ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)組態檔元素。</span><span class="sxs-lookup"><span data-stu-id="efce5-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="efce5-116">指定的 common language runtime (CLR)，應該統一原則。</span><span class="sxs-lookup"><span data-stu-id="efce5-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efce5-117">備註</span><span class="sxs-lookup"><span data-stu-id="efce5-117">Remarks</span></span>  
 <span data-ttu-id="efce5-118">此列舉會傳遞至方法的[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)介面以指定在應用程式原則的變更。</span><span class="sxs-lookup"><span data-stu-id="efce5-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efce5-119">需求</span><span class="sxs-lookup"><span data-stu-id="efce5-119">Requirements</span></span>  
 <span data-ttu-id="efce5-120">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efce5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efce5-121">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efce5-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efce5-122">**程式庫：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efce5-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efce5-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efce5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efce5-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="efce5-124">See Also</span></span>  
 [<span data-ttu-id="efce5-125">ICLRAssemblyIdentityManager 介面</span><span class="sxs-lookup"><span data-stu-id="efce5-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="efce5-126">裝載列舉</span><span class="sxs-lookup"><span data-stu-id="efce5-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)