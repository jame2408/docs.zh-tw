---
title: ICorDebugEval2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a><span data-ttu-id="f3ea7-102">ICorDebugEval2 Interface1</span><span class="sxs-lookup"><span data-stu-id="f3ea7-102">ICorDebugEval2 Interface1</span></span>
<span data-ttu-id="f3ea7-103">擴充 「 ICorDebugEval 「 泛型型別提供支援。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3ea7-104">方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-104">Methods</span></span>  
  
|<span data-ttu-id="f3ea7-105">方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-105">Method</span></span>|<span data-ttu-id="f3ea7-106">說明</span><span class="sxs-lookup"><span data-stu-id="f3ea7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3ea7-107">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="f3ea7-108">設定指定"ICorDebugFunction"，這可以巢狀的建構函式會採用型別參數，或本身可以採用型別參數的類型內部的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="f3ea7-109">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="f3ea7-110">取得新的 「 ICorDebugValue"指定的類型，具有指標初始值為 null 或零。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="f3ea7-111">NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="f3ea7-112">配置的指定項目類型和維度的新陣列。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="f3ea7-113">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="f3ea7-114">具現化新的參數化的型別物件，並呼叫物件的建構函式方法。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="f3ea7-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="f3ea7-116">而不會嘗試呼叫建構函式方法會指定類別的新參數化型的別物件具現化</span><span class="sxs-lookup"><span data-stu-id="f3ea7-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="f3ea7-117">NewStringWithLength 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="f3ea7-118">具有指定的內容來建立新的指定長度的字串。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="f3ea7-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="f3ea7-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="f3ea7-120">中止計算此`ICorDebugEval2`目前正在執行。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3ea7-121">備註</span><span class="sxs-lookup"><span data-stu-id="f3ea7-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3ea7-122">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ea7-123">需求</span><span class="sxs-lookup"><span data-stu-id="f3ea7-123">Requirements</span></span>  
 <span data-ttu-id="f3ea7-124">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ea7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ea7-125">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3ea7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3ea7-126">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3ea7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3ea7-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ea7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ea7-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3ea7-128">See Also</span></span>  
 [<span data-ttu-id="f3ea7-129">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="f3ea7-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)