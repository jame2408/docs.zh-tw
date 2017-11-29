---
title: "ICorDebugRemote::DebugActiveProcessEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.DebugActiveProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a0fe75c29334501bbccc101f5fa079501536ce5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="4911a-102">ICorDebugRemote::DebugActiveProcessEx 方法</span><span class="sxs-lookup"><span data-stu-id="4911a-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="4911a-103">啟動處理序在偵錯工具在遠端電腦上。</span><span class="sxs-lookup"><span data-stu-id="4911a-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4911a-104">語法</span><span class="sxs-lookup"><span data-stu-id="4911a-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4911a-105">參數</span><span class="sxs-lookup"><span data-stu-id="4911a-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="4911a-106">[in]指標[ICorDebugRemoteTarget 介面](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="4911a-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="4911a-107">這個參數用來判斷處理程序執行所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="4911a-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="4911a-108">[in]是要附加偵錯工具處理序的識別碼。</span><span class="sxs-lookup"><span data-stu-id="4911a-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="4911a-109">[in]`true`如果偵錯工具時應做為 Win32 偵錯工具處理序的行為及分派 unmanaged 的回呼中; 否則`false`。</span><span class="sxs-lookup"><span data-stu-id="4911a-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4911a-110">[out]表示要附加偵錯工具的程序的"ICorDebugProcess 」 物件的位址指標。</span><span class="sxs-lookup"><span data-stu-id="4911a-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4911a-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="4911a-111">Return Value</span></span>  
 <span data-ttu-id="4911a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4911a-112">S_OK</span></span>  
 <span data-ttu-id="4911a-113">已成功連接至遠端電腦上的處理序。</span><span class="sxs-lookup"><span data-stu-id="4911a-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="4911a-114">E_FAIL (或其他 E_ 傳回碼)</span><span class="sxs-lookup"><span data-stu-id="4911a-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4911a-115">無法附加至遠端電腦上的處理序。</span><span class="sxs-lookup"><span data-stu-id="4911a-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4911a-116">備註</span><span class="sxs-lookup"><span data-stu-id="4911a-116">Remarks</span></span>  
 <span data-ttu-id="4911a-117">Silverlight 中不支援混合模式偵錯。</span><span class="sxs-lookup"><span data-stu-id="4911a-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4911a-118">需求</span><span class="sxs-lookup"><span data-stu-id="4911a-118">Requirements</span></span>  
 <span data-ttu-id="4911a-119">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4911a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4911a-120">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4911a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4911a-121">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4911a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4911a-122">**.NET framework 版本：** 4.5、 4、 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4911a-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4911a-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4911a-123">See Also</span></span>  
 [<span data-ttu-id="4911a-124">ICorDebugRemote 介面</span><span class="sxs-lookup"><span data-stu-id="4911a-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="4911a-125">ICorDebug 介面</span><span class="sxs-lookup"><span data-stu-id="4911a-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="4911a-126">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="4911a-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)