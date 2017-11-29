---
title: "ICLRDebugManager::IsDebuggerAttached 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 986c9ab7853324d1a2f0fc104399141068ae9a09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="f4cb3-102">ICLRDebugManager::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="f4cb3-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="f4cb3-103">取得值，表示偵錯工具是否附加至處理序。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4cb3-104">語法</span><span class="sxs-lookup"><span data-stu-id="f4cb3-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4cb3-105">參數</span><span class="sxs-lookup"><span data-stu-id="f4cb3-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="f4cb3-106">[out]`true`偵錯工具是否附加至處理程序，否則`false`。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4cb3-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="f4cb3-107">Return Value</span></span>  
  
|<span data-ttu-id="f4cb3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4cb3-108">HRESULT</span></span>|<span data-ttu-id="f4cb3-109">描述</span><span class="sxs-lookup"><span data-stu-id="f4cb3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4cb3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4cb3-110">S_OK</span></span>|<span data-ttu-id="f4cb3-111">`IsDebuggerAttached`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="f4cb3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4cb3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4cb3-113">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4cb3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4cb3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4cb3-115">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-115">The call timed out.</span></span>|  
|<span data-ttu-id="f4cb3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4cb3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4cb3-117">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4cb3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4cb3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4cb3-119">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4cb3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4cb3-120">E_FAIL</span></span>|<span data-ttu-id="f4cb3-121">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4cb3-122">方法會傳回 E_FAIL 之後，CLR 就不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4cb3-123">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4cb3-124">備註</span><span class="sxs-lookup"><span data-stu-id="f4cb3-124">Remarks</span></span>  
 <span data-ttu-id="f4cb3-125">`IsDebuggerAttached`可讓主應用程式查詢來判斷是否要將偵錯工具附加至處理序的 CLR。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4cb3-126">需求</span><span class="sxs-lookup"><span data-stu-id="f4cb3-126">Requirements</span></span>  
 <span data-ttu-id="f4cb3-127">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cb3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4cb3-128">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4cb3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4cb3-129">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="f4cb3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4cb3-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4cb3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4cb3-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4cb3-131">See Also</span></span>  
 [<span data-ttu-id="f4cb3-132">ICLRControl 介面</span><span class="sxs-lookup"><span data-stu-id="f4cb3-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f4cb3-133">ICLRDebugManager 介面</span><span class="sxs-lookup"><span data-stu-id="f4cb3-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="f4cb3-134">IHostControl 介面</span><span class="sxs-lookup"><span data-stu-id="f4cb3-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)