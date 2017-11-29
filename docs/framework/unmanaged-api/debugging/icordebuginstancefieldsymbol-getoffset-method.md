---
title: "ICorDebugInstanceFieldSymbol::GetOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="fa7f4-102">ICorDebugInstanceFieldSymbol::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="fa7f4-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="fa7f4-103">取得此執行個體欄位在其父類別中的位移 (以位元組為單位)。</span><span class="sxs-lookup"><span data-stu-id="fa7f4-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7f4-104">語法</span><span class="sxs-lookup"><span data-stu-id="fa7f4-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa7f4-105">參數</span><span class="sxs-lookup"><span data-stu-id="fa7f4-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="fa7f4-106">此執行個體欄位在其父類別中的位移位元組數目。</span><span class="sxs-lookup"><span data-stu-id="fa7f4-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa7f4-107">備註</span><span class="sxs-lookup"><span data-stu-id="fa7f4-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa7f4-108">這個方法僅適用於 .NET 原生。</span><span class="sxs-lookup"><span data-stu-id="fa7f4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7f4-109">需求</span><span class="sxs-lookup"><span data-stu-id="fa7f4-109">Requirements</span></span>  
 <span data-ttu-id="fa7f4-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa7f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7f4-111">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa7f4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa7f4-112">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa7f4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa7f4-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7f4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7f4-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fa7f4-114">See Also</span></span>  
 [<span data-ttu-id="fa7f4-115">ICorDebugInstanceFieldSymbol 介面</span><span class="sxs-lookup"><span data-stu-id="fa7f4-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="fa7f4-116">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="fa7f4-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)