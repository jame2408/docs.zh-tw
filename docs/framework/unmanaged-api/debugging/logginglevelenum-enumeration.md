---
title: "LoggingLevelEnum 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f6041f429c057cea9607df34ec5691be84e2d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="8af95-102">LoggingLevelEnum 列舉</span><span class="sxs-lookup"><span data-stu-id="8af95-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="8af95-103">指出當 Managed 執行緒記錄事件時，寫入至事件記錄檔之描述性訊息的嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="8af95-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af95-104">語法</span><span class="sxs-lookup"><span data-stu-id="8af95-104">Syntax</span></span>  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="8af95-105">成員</span><span class="sxs-lookup"><span data-stu-id="8af95-105">Members</span></span>  
  
|<span data-ttu-id="8af95-106">成員</span><span class="sxs-lookup"><span data-stu-id="8af95-106">Member</span></span>|<span data-ttu-id="8af95-107">說明</span><span class="sxs-lookup"><span data-stu-id="8af95-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="8af95-108">此訊息為 「 追蹤層級 0。</span><span class="sxs-lookup"><span data-stu-id="8af95-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="8af95-109">追蹤層級 1 的訊息。</span><span class="sxs-lookup"><span data-stu-id="8af95-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="8af95-110">追蹤層級 2 的訊息。</span><span class="sxs-lookup"><span data-stu-id="8af95-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="8af95-111">此訊息為 「 追蹤層級 3。</span><span class="sxs-lookup"><span data-stu-id="8af95-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="8af95-112">此訊息為 「 追蹤層級 4。</span><span class="sxs-lookup"><span data-stu-id="8af95-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="8af95-113">此訊息為狀態層級 0。</span><span class="sxs-lookup"><span data-stu-id="8af95-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="8af95-114">此訊息為狀態層級 1。</span><span class="sxs-lookup"><span data-stu-id="8af95-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="8af95-115">此訊息為狀態層級 2。</span><span class="sxs-lookup"><span data-stu-id="8af95-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="8af95-116">此訊息為狀態層級 3。</span><span class="sxs-lookup"><span data-stu-id="8af95-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="8af95-117">此訊息為狀態層級 4。</span><span class="sxs-lookup"><span data-stu-id="8af95-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="8af95-118">訊息是警告層級。</span><span class="sxs-lookup"><span data-stu-id="8af95-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="8af95-119">錯誤層級的訊息。</span><span class="sxs-lookup"><span data-stu-id="8af95-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="8af95-120">此訊息為異常的層級。</span><span class="sxs-lookup"><span data-stu-id="8af95-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af95-121">備註</span><span class="sxs-lookup"><span data-stu-id="8af95-121">Remarks</span></span>  
 <span data-ttu-id="8af95-122">Common language runtime (CLR) 呼叫[icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)方法來通知偵錯工具 managed 的執行緒已記錄事件。</span><span class="sxs-lookup"><span data-stu-id="8af95-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="8af95-123">CLR 值傳遞給`LoggingLevelEnum`表示 managed 的執行緒已寫入事件記錄檔訊息的嚴重性層級的列舉。</span><span class="sxs-lookup"><span data-stu-id="8af95-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af95-124">需求</span><span class="sxs-lookup"><span data-stu-id="8af95-124">Requirements</span></span>  
 <span data-ttu-id="8af95-125">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8af95-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af95-126">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8af95-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8af95-127">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8af95-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8af95-128">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af95-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af95-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8af95-129">See Also</span></span>  
 <xref:System.Diagnostics.EventLog>  
 [<span data-ttu-id="8af95-130">偵錯列舉</span><span class="sxs-lookup"><span data-stu-id="8af95-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)