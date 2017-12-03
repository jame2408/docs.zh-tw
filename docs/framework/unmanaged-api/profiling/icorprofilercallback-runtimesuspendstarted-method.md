---
title: "ICorProfilerCallback::RuntimeSuspendStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="30032-102">ICorProfilerCallback::RuntimeSuspendStarted 方法</span><span class="sxs-lookup"><span data-stu-id="30032-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="30032-103">通知分析工具執行階段即將暫停執行階段的所有執行緒。</span><span class="sxs-lookup"><span data-stu-id="30032-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30032-104">語法</span><span class="sxs-lookup"><span data-stu-id="30032-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30032-105">參數</span><span class="sxs-lookup"><span data-stu-id="30032-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="30032-106">[in]值為[COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)列舉，指出暫止的原因。</span><span class="sxs-lookup"><span data-stu-id="30032-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30032-107">備註</span><span class="sxs-lookup"><span data-stu-id="30032-107">Remarks</span></span>  
 <span data-ttu-id="30032-108">允許在 unmanaged 程式碼中的所有執行階段執行緒繼續執行，直到嘗試重新進入執行階段。</span><span class="sxs-lookup"><span data-stu-id="30032-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="30032-109">此時，它們也會被暫止直到執行階段繼續。</span><span class="sxs-lookup"><span data-stu-id="30032-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="30032-110">這也適用於新的執行緒進入執行階段。</span><span class="sxs-lookup"><span data-stu-id="30032-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="30032-111">執行階段中的所有執行緒都都在立即暫止都已中斷的程式碼，或者都會要求他們在到達可中斷的程式碼時暫停。</span><span class="sxs-lookup"><span data-stu-id="30032-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30032-112">需求</span><span class="sxs-lookup"><span data-stu-id="30032-112">Requirements</span></span>  
 <span data-ttu-id="30032-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30032-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30032-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30032-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30032-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30032-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30032-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30032-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30032-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="30032-117">See Also</span></span>  
 [<span data-ttu-id="30032-118">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="30032-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="30032-119">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="30032-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="30032-120">RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="30032-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)