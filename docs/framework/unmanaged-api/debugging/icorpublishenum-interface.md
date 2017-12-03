---
title: "ICorPublishEnum 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="20986-102">ICorPublishEnum 介面</span><span class="sxs-lookup"><span data-stu-id="20986-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="20986-103">做為處理程序和應用程式定義域的相關資訊的發行中所使用的列舉值的抽象基底介面。</span><span class="sxs-lookup"><span data-stu-id="20986-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20986-104">方法</span><span class="sxs-lookup"><span data-stu-id="20986-104">Methods</span></span>  
  
|<span data-ttu-id="20986-105">方法</span><span class="sxs-lookup"><span data-stu-id="20986-105">Method</span></span>|<span data-ttu-id="20986-106">說明</span><span class="sxs-lookup"><span data-stu-id="20986-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20986-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="20986-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="20986-108">建立一份這`ICorPublishEnum`物件。</span><span class="sxs-lookup"><span data-stu-id="20986-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="20986-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="20986-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="20986-110">列舉中取得的項目數。</span><span class="sxs-lookup"><span data-stu-id="20986-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="20986-111">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="20986-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="20986-112">將游標移至列舉的開頭。</span><span class="sxs-lookup"><span data-stu-id="20986-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="20986-113">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="20986-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="20986-114">將游標移往前列舉中所指定的項目數。</span><span class="sxs-lookup"><span data-stu-id="20986-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20986-115">備註</span><span class="sxs-lookup"><span data-stu-id="20986-115">Remarks</span></span>  
 <span data-ttu-id="20986-116">下列的列舉值衍生自`ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="20986-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="20986-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="20986-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="20986-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="20986-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="20986-119">需求</span><span class="sxs-lookup"><span data-stu-id="20986-119">Requirements</span></span>  
 <span data-ttu-id="20986-120">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20986-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20986-121">**標頭：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="20986-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="20986-122">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20986-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20986-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20986-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20986-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="20986-124">See Also</span></span>  
 [<span data-ttu-id="20986-125">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="20986-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="20986-126">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="20986-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)