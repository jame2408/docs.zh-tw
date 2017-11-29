---
title: "ICorDebugVariableHome::GetOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="0fcd3-102">ICorDebugVariableHome::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0fcd3-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="0fcd3-103">取得從基底暫存器變數位移。</span><span class="sxs-lookup"><span data-stu-id="0fcd3-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcd3-104">語法</span><span class="sxs-lookup"><span data-stu-id="0fcd3-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fcd3-105">參數</span><span class="sxs-lookup"><span data-stu-id="0fcd3-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="0fcd3-106">[out]基底暫存器從位移。</span><span class="sxs-lookup"><span data-stu-id="0fcd3-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fcd3-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="0fcd3-107">Return Value</span></span>  
 <span data-ttu-id="0fcd3-108">方法會傳回下列值：</span><span class="sxs-lookup"><span data-stu-id="0fcd3-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="0fcd3-109">值</span><span class="sxs-lookup"><span data-stu-id="0fcd3-109">Value</span></span>|<span data-ttu-id="0fcd3-110">說明</span><span class="sxs-lookup"><span data-stu-id="0fcd3-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="0fcd3-111">變數是在暫存器的相對記憶體位置。</span><span class="sxs-lookup"><span data-stu-id="0fcd3-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="0fcd3-112">變數不是在暫存器的相對記憶體位置。</span><span class="sxs-lookup"><span data-stu-id="0fcd3-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fcd3-113">需求</span><span class="sxs-lookup"><span data-stu-id="0fcd3-113">Requirements</span></span>  
 <span data-ttu-id="0fcd3-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fcd3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fcd3-115">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fcd3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fcd3-116">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fcd3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fcd3-117">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fcd3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcd3-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0fcd3-118">See Also</span></span>  
 [<span data-ttu-id="0fcd3-119">ICorDebugVariableHome 介面</span><span class="sxs-lookup"><span data-stu-id="0fcd3-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)