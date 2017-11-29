---
title: "ICorProfilerInfo::GetEventMask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetEventMask
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8757298819f5ca6a534a12cec0593aed05610042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="2604c-102">ICorProfilerInfo::GetEventMask 方法</span><span class="sxs-lookup"><span data-stu-id="2604c-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="2604c-103">取得分析工具想要從 Common Language Runtime (CLR) 接收事件通知的目前事件分類。</span><span class="sxs-lookup"><span data-stu-id="2604c-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2604c-104">語法</span><span class="sxs-lookup"><span data-stu-id="2604c-104">Syntax</span></span>  
  
```  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2604c-105">參數</span><span class="sxs-lookup"><span data-stu-id="2604c-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="2604c-106">[out] 指定事件分類的 4 位元組值的指標。</span><span class="sxs-lookup"><span data-stu-id="2604c-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="2604c-107">每個位元分別控制不同的功能、行為或事件類型。</span><span class="sxs-lookup"><span data-stu-id="2604c-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="2604c-108">中所述的位元[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列舉型別。</span><span class="sxs-lookup"><span data-stu-id="2604c-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2604c-109">備註</span><span class="sxs-lookup"><span data-stu-id="2604c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2604c-110">您應該呼叫[GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)方法，而不是此方法。</span><span class="sxs-lookup"><span data-stu-id="2604c-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="2604c-111">雖然`SetEventMask`方法會繼續受到支援， [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)提供額外的功能。</span><span class="sxs-lookup"><span data-stu-id="2604c-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2604c-112">需求</span><span class="sxs-lookup"><span data-stu-id="2604c-112">Requirements</span></span>  
 <span data-ttu-id="2604c-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2604c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2604c-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2604c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2604c-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2604c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2604c-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2604c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2604c-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2604c-117">See Also</span></span>  
 [<span data-ttu-id="2604c-118">GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="2604c-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)  
 [<span data-ttu-id="2604c-119">ICorProfilerInfo 介面</span><span class="sxs-lookup"><span data-stu-id="2604c-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)