---
title: "ICorDebugProcess6 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 222007d03d8ace00f97c01cf2a02f0dc293bbf78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="ab3df-102">ICorDebugProcess6 介面</span><span class="sxs-lookup"><span data-stu-id="ab3df-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="ab3df-103">以邏輯方式擴充 ICorDebugProcess 介面，以啟用功能，例如解碼會以原生例外狀況偵錯事件，以及虛擬模組分割編碼的 managed 偵錯事件。</span><span class="sxs-lookup"><span data-stu-id="ab3df-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab3df-104">方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-104">Methods</span></span>  
  
|<span data-ttu-id="ab3df-105">方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-105">Method</span></span>|<span data-ttu-id="ab3df-106">說明</span><span class="sxs-lookup"><span data-stu-id="ab3df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab3df-107">DecodeEvent 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="ab3df-108">對已封裝在特殊設計之原生例外狀況偵錯事件承載中的 Managed 偵錯事件進行解碼。</span><span class="sxs-lookup"><span data-stu-id="ab3df-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="ab3df-109">EnableVirtualModuleSplitting 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="ab3df-110">啟用或停用虛擬模組分割。</span><span class="sxs-lookup"><span data-stu-id="ab3df-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="ab3df-111">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="ab3df-112">取得特定程式碼位址之 Managed 程式碼的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ab3df-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="ab3df-113">GetExportStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="ab3df-114">提供執行階段匯出函式的相關資訊，以協助逐步執行 Managed 程式碼。</span><span class="sxs-lookup"><span data-stu-id="ab3df-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="ab3df-115">MarkDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="ab3df-116">變更偵錯項目的內部狀態，讓 .NET Framework 類別庫中的 <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> 方法傳回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ab3df-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="ab3df-117">ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="ab3df-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="ab3df-118">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)處理序正在執行。</span><span class="sxs-lookup"><span data-stu-id="ab3df-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab3df-119">備註</span><span class="sxs-lookup"><span data-stu-id="ab3df-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab3df-120">這個介面僅適用於 .NET 原生。</span><span class="sxs-lookup"><span data-stu-id="ab3df-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="ab3df-121">嘗試在 .NET 原生之外的 ICorDebug 案例中呼叫 `QueryInterface` 以擷取介面指標，會傳回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="ab3df-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab3df-122">需求</span><span class="sxs-lookup"><span data-stu-id="ab3df-122">Requirements</span></span>  
 <span data-ttu-id="ab3df-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab3df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab3df-124">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab3df-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab3df-125">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab3df-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab3df-126">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab3df-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3df-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ab3df-127">See Also</span></span>  
 [<span data-ttu-id="ab3df-128">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="ab3df-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ab3df-129">偵錯</span><span class="sxs-lookup"><span data-stu-id="ab3df-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)