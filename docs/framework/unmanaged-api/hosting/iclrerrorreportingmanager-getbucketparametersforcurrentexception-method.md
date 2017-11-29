---
title: "ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80bf3e9b1cee9f19534f985dccf4508467dbe26e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="8f9ba-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="8f9ba-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="8f9ba-103">取得目前的例外狀況呼叫的執行緒上的 Watson 貯體。</span><span class="sxs-lookup"><span data-stu-id="8f9ba-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="8f9ba-104">A*貯體*是相同程式碼的缺失相關的錯誤資料的集合。</span><span class="sxs-lookup"><span data-stu-id="8f9ba-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="8f9ba-105">*Watson*指一組技術，用於收集和分析與例外狀況相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="8f9ba-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9ba-106">語法</span><span class="sxs-lookup"><span data-stu-id="8f9ba-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f9ba-107">參數</span><span class="sxs-lookup"><span data-stu-id="8f9ba-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="8f9ba-108">[out]指標[BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)包含例外狀況的錯誤資料的結構。</span><span class="sxs-lookup"><span data-stu-id="8f9ba-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f9ba-109">需求</span><span class="sxs-lookup"><span data-stu-id="8f9ba-109">Requirements</span></span>  
 <span data-ttu-id="8f9ba-110">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f9ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f9ba-111">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f9ba-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f9ba-112">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="8f9ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f9ba-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f9ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9ba-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8f9ba-114">See Also</span></span>  
 [<span data-ttu-id="8f9ba-115">ICLRErrorReportingManager 介面</span><span class="sxs-lookup"><span data-stu-id="8f9ba-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)