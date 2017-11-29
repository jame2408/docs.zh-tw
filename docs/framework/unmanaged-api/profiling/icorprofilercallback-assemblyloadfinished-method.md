---
title: "ICorProfilerCallback::AssemblyLoadFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af5089603c2044b10061a32c5921b9eeadf86b36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="4bf93-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4bf93-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="4bf93-103">通知分析工具組件已完成載入。</span><span class="sxs-lookup"><span data-stu-id="4bf93-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf93-104">語法</span><span class="sxs-lookup"><span data-stu-id="4bf93-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bf93-105">參數</span><span class="sxs-lookup"><span data-stu-id="4bf93-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="4bf93-106">[in]識別已載入的組件。</span><span class="sxs-lookup"><span data-stu-id="4bf93-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4bf93-107">[in]HRESULT 值，指出是否已經完成組件載入成功。</span><span class="sxs-lookup"><span data-stu-id="4bf93-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bf93-108">備註</span><span class="sxs-lookup"><span data-stu-id="4bf93-108">Remarks</span></span>  
 <span data-ttu-id="4bf93-109">值`assemblyId`不正確的資訊要求，直到`AssemblyLoadFinished`方法呼叫。</span><span class="sxs-lookup"><span data-stu-id="4bf93-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="4bf93-110">載入組件的某些部分可能會繼續之後`AssemblyLoadFinished`回呼。</span><span class="sxs-lookup"><span data-stu-id="4bf93-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="4bf93-111">失敗的 HRESULT 中`hrStatus`表示失敗。</span><span class="sxs-lookup"><span data-stu-id="4bf93-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4bf93-112">不過，成功 HRESULT 中`hrStatus`只會指出已成功載入組件的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="4bf93-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf93-113">需求</span><span class="sxs-lookup"><span data-stu-id="4bf93-113">Requirements</span></span>  
 <span data-ttu-id="4bf93-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf93-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf93-115">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bf93-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bf93-116">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bf93-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bf93-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf93-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf93-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4bf93-118">See Also</span></span>  
 [<span data-ttu-id="4bf93-119">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="4bf93-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)