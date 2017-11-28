---
title: "ICLRStrongName::GetHashFromHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01fefe99e82584267b3c0f3e0e528dd798affa15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="9df9f-102">ICLRStrongName::GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="9df9f-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="9df9f-103">具有指定的檔案控制代碼，使用指定的雜湊演算法之檔案的內容中產生之雜湊。</span><span class="sxs-lookup"><span data-stu-id="9df9f-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df9f-104">語法</span><span class="sxs-lookup"><span data-stu-id="9df9f-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9df9f-105">參數</span><span class="sxs-lookup"><span data-stu-id="9df9f-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="9df9f-106">[in]要雜湊的檔案控制代碼。</span><span class="sxs-lookup"><span data-stu-id="9df9f-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9df9f-107">[in、 out]常數，指定的雜湊演算法。</span><span class="sxs-lookup"><span data-stu-id="9df9f-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9df9f-108">使用預設演算法為零。</span><span class="sxs-lookup"><span data-stu-id="9df9f-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9df9f-109">[out]傳回雜湊緩衝區。</span><span class="sxs-lookup"><span data-stu-id="9df9f-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9df9f-110">[in]要求的大小上限的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="9df9f-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9df9f-111">[out]大小，以位元組為單位傳回`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="9df9f-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9df9f-112">傳回值</span><span class="sxs-lookup"><span data-stu-id="9df9f-112">Return Value</span></span>  
 <span data-ttu-id="9df9f-113">`S_OK`如果方法成功。否則，表示失敗的 HRESULT 值 (請參閱[常見的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)清單)。</span><span class="sxs-lookup"><span data-stu-id="9df9f-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9df9f-114">需求</span><span class="sxs-lookup"><span data-stu-id="9df9f-114">Requirements</span></span>  
 <span data-ttu-id="9df9f-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9df9f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9df9f-116">**標頭：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9df9f-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9df9f-117">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="9df9f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9df9f-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df9f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df9f-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9df9f-119">See Also</span></span>  
 [<span data-ttu-id="9df9f-120">ICLRStrongName 介面</span><span class="sxs-lookup"><span data-stu-id="9df9f-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)