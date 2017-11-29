---
title: "ICorPublishAppDomainEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79b9ad5711ac1d0166a7ad328cc227f17780476c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="990dc-102">ICorPublishAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="990dc-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="990dc-103">在過程中，從目前位置開始，取得目前存在的應用程式定義域指定的數目。</span><span class="sxs-lookup"><span data-stu-id="990dc-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="990dc-104">語法</span><span class="sxs-lookup"><span data-stu-id="990dc-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="990dc-105">參數</span><span class="sxs-lookup"><span data-stu-id="990dc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="990dc-106">[in]要擷取的項目數目。</span><span class="sxs-lookup"><span data-stu-id="990dc-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="990dc-107">[out]陣列指標擷取[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)物件，其中每個代表應用程式定義域。</span><span class="sxs-lookup"><span data-stu-id="990dc-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="990dc-108">[out]指向實際傳回的應用程式定義域數目。</span><span class="sxs-lookup"><span data-stu-id="990dc-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="990dc-109">這個值可以是 null 如果`celt`是其中一個。</span><span class="sxs-lookup"><span data-stu-id="990dc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="990dc-110">需求</span><span class="sxs-lookup"><span data-stu-id="990dc-110">Requirements</span></span>  
 <span data-ttu-id="990dc-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="990dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="990dc-112">**標頭：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="990dc-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="990dc-113">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="990dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="990dc-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="990dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990dc-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="990dc-115">See Also</span></span>  
 [<span data-ttu-id="990dc-116">ICorPublishAppDomainEnum 介面</span><span class="sxs-lookup"><span data-stu-id="990dc-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)