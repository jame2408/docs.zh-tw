---
title: "ICorDebugILCode2::GetInstrumentedILMap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b740f378b4fd15fe6bf4a9832348869878e2a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="45930-102">ICorDebugILCode2::GetInstrumentedILMap 方法</span><span class="sxs-lookup"><span data-stu-id="45930-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="45930-103">[在 .NET Framework 4.5.2 及更新版本中支援]</span><span class="sxs-lookup"><span data-stu-id="45930-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="45930-104">將對應從分析工具檢測中繼語言 (IL) 位移傳回至此執行個體的原始方法 IL 位移。</span><span class="sxs-lookup"><span data-stu-id="45930-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45930-105">語法</span><span class="sxs-lookup"><span data-stu-id="45930-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45930-106">參數</span><span class="sxs-lookup"><span data-stu-id="45930-106">Parameters</span></span>  
 <span data-ttu-id="45930-107">cMap</span><span class="sxs-lookup"><span data-stu-id="45930-107">cMap</span></span>  
 <span data-ttu-id="45930-108">[in] `map` 陣列的儲存體容量。</span><span class="sxs-lookup"><span data-stu-id="45930-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="45930-109">如需詳細資訊，請參閱「備註」一節。</span><span class="sxs-lookup"><span data-stu-id="45930-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="45930-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="45930-110">pcMap</span></span>  
 <span data-ttu-id="45930-111">[out]寫入至對應陣列的 COR_IL_MAP 值數目。</span><span class="sxs-lookup"><span data-stu-id="45930-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="45930-112">map</span><span class="sxs-lookup"><span data-stu-id="45930-112">map</span></span>  
 <span data-ttu-id="45930-113">[out]可提供有關對應從分析工具檢測 IL 的原始方法 il COR_IL_MAP 值的陣列。</span><span class="sxs-lookup"><span data-stu-id="45930-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45930-114">備註</span><span class="sxs-lookup"><span data-stu-id="45930-114">Remarks</span></span>  
 <span data-ttu-id="45930-115">如果分析工具來設定對應藉由呼叫[icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)方法，偵錯工具可以呼叫這個方法來擷取對應，並計算 IL 位移堆疊時，在內部使用對應追蹤及變數存留期。</span><span class="sxs-lookup"><span data-stu-id="45930-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="45930-116">如果`cMap`為 0 和`pcMap`是非**null**，`pcMap`設為 可用的 COR_IL_MAP 值數目。</span><span class="sxs-lookup"><span data-stu-id="45930-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="45930-117">若 `cMap` 為非零，其代表 `map` 陣列的儲存容量。</span><span class="sxs-lookup"><span data-stu-id="45930-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="45930-118">方法傳回時，`map`包含最多`cMap`項目，和`pcMap`設定為實際寫入至 COR_IL_MAP 值數目`map`陣列。</span><span class="sxs-lookup"><span data-stu-id="45930-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="45930-119">如果 IL 未經檢測，或是分析工具未提供對應，此方法會傳回 `S_OK`，並將 `pcMap` 設為 0。</span><span class="sxs-lookup"><span data-stu-id="45930-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45930-120">需求</span><span class="sxs-lookup"><span data-stu-id="45930-120">Requirements</span></span>  
 <span data-ttu-id="45930-121">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45930-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45930-122">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45930-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45930-123">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45930-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45930-124">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45930-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45930-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="45930-125">See Also</span></span>  
 [<span data-ttu-id="45930-126">Icorprofilerinfo:: Setilinstrumentedcodemap</span><span class="sxs-lookup"><span data-stu-id="45930-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [<span data-ttu-id="45930-127">ICorDebugILCode2 介面</span><span class="sxs-lookup"><span data-stu-id="45930-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="45930-128">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="45930-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)