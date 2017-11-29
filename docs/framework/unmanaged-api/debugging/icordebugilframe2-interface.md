---
title: ICorDebugILFrame2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 759232d5c1e5bdf00c85145fa0fc3d69743c13f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="f1176-102">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="f1176-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="f1176-103">ICorDebugILFrame 介面邏輯擴充。</span><span class="sxs-lookup"><span data-stu-id="f1176-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1176-104">方法</span><span class="sxs-lookup"><span data-stu-id="f1176-104">Methods</span></span>  
  
|<span data-ttu-id="f1176-105">方法</span><span class="sxs-lookup"><span data-stu-id="f1176-105">Method</span></span>|<span data-ttu-id="f1176-106">說明</span><span class="sxs-lookup"><span data-stu-id="f1176-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1176-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="f1176-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="f1176-108">取得包含 ICorDebugTypeEnum 物件<xref:System.Type>這個框架中的參數。</span><span class="sxs-lookup"><span data-stu-id="f1176-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="f1176-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="f1176-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="f1176-110">重新對應已編輯函式，藉由指定新的 MSIL 位移。</span><span class="sxs-lookup"><span data-stu-id="f1176-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1176-111">備註</span><span class="sxs-lookup"><span data-stu-id="f1176-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1176-112">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="f1176-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1176-113">需求</span><span class="sxs-lookup"><span data-stu-id="f1176-113">Requirements</span></span>  
 <span data-ttu-id="f1176-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1176-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1176-115">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1176-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1176-116">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1176-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1176-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1176-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1176-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1176-118">See Also</span></span>  
 [<span data-ttu-id="f1176-119">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="f1176-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)