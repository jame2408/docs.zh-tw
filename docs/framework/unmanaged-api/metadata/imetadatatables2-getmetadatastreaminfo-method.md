---
title: "IMetaDataTables2::GetMetaDataStreamInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStreamInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1631ae8398a8daa910931ff705440a2be0cf21b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="f5054-102">IMetaDataTables2::GetMetaDataStreamInfo 方法</span><span class="sxs-lookup"><span data-stu-id="f5054-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="f5054-103">取得名稱、 大小和指定之索引處的中繼資料資料流內容。</span><span class="sxs-lookup"><span data-stu-id="f5054-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5054-104">語法</span><span class="sxs-lookup"><span data-stu-id="f5054-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5054-105">參數</span><span class="sxs-lookup"><span data-stu-id="f5054-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="f5054-106">[in]要求的中繼資料資料流的索引。</span><span class="sxs-lookup"><span data-stu-id="f5054-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="f5054-107">[out]指標的資料流名稱。</span><span class="sxs-lookup"><span data-stu-id="f5054-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="f5054-108">[out]中繼資料資料流的指標。</span><span class="sxs-lookup"><span data-stu-id="f5054-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="f5054-109">[out]大小，以位元組為單位的`ppv`。</span><span class="sxs-lookup"><span data-stu-id="f5054-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5054-110">需求</span><span class="sxs-lookup"><span data-stu-id="f5054-110">Requirements</span></span>  
 <span data-ttu-id="f5054-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5054-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5054-112">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5054-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5054-113">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="f5054-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5054-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5054-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5054-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5054-115">See Also</span></span>  
 [<span data-ttu-id="f5054-116">IMetaDataTables2 介面</span><span class="sxs-lookup"><span data-stu-id="f5054-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="f5054-117">IMetaDataTables 介面</span><span class="sxs-lookup"><span data-stu-id="f5054-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)