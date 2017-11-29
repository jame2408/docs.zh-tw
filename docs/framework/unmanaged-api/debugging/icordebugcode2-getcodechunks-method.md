---
title: "ICorDebugCode2::GetCodeChunks 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCodeChunks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 950fd5c19e8827a63dcf075c42d3e0c18ff91261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="a5b45-102">ICorDebugCode2::GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="a5b45-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="a5b45-103">取得這個程式碼物件組成的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="a5b45-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b45-104">語法</span><span class="sxs-lookup"><span data-stu-id="a5b45-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5b45-105">參數</span><span class="sxs-lookup"><span data-stu-id="a5b45-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="a5b45-106">[in]大小`chunks`陣列。</span><span class="sxs-lookup"><span data-stu-id="a5b45-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="a5b45-107">[out]區塊中傳回的數目`chunks`陣列。</span><span class="sxs-lookup"><span data-stu-id="a5b45-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="a5b45-108">[out]結構的陣列 」 CodeChunkInfo"，其中每一個都代表單一的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="a5b45-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="a5b45-109">如果值`cbufSize`是 0，這個參數可以是 null。</span><span class="sxs-lookup"><span data-stu-id="a5b45-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5b45-110">備註</span><span class="sxs-lookup"><span data-stu-id="a5b45-110">Remarks</span></span>  
 <span data-ttu-id="a5b45-111">程式碼區塊將會永遠不會重疊，而且它們會將遵照的順序中串連這些區塊會有已由[Icordebugcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a5b45-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="a5b45-112">在.NET Framework 2.0 版的 Microsoft intermediate language (MSIL) 程式碼物件將由一個單一程式碼區塊所組成。</span><span class="sxs-lookup"><span data-stu-id="a5b45-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b45-113">需求</span><span class="sxs-lookup"><span data-stu-id="a5b45-113">Requirements</span></span>  
 <span data-ttu-id="a5b45-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5b45-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b45-115">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5b45-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5b45-116">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5b45-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5b45-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b45-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b45-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a5b45-118">See Also</span></span>  
 