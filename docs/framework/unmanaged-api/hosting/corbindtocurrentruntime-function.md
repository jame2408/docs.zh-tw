---
title: CorBindToCurrentRuntime 函式
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021f2b7a720c2190d56bdb2b35214c581a7b5f56
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44088046"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime 函式
載入處理序的 common language runtime (CLR) 使用的 XML 檔案中儲存的版本資訊。 XML 檔案的格式被仿造自標準的應用程式組態檔。 如需組態檔的詳細資訊，請參閱[組態檔結構描述](../../../../docs/framework/configure-apps/file-schema/index.md)。  
  
 此函式中的過時[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 請參閱[Common Language Runtime 載入處理序](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pwszFileName`  
 [in]指定要載入的 clr 版本的應用程式組態檔的名稱。 如果檔案名稱的格式不完整，則會假設是在進行呼叫的可執行檔相同的目錄中。  
  
 Version 屬性中所描述要載入的執行階段版本[ \<Requiredruntime> >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)組態檔的項目。  
  
 如果未指定版本，或如果`<requiredRuntime>`找不到項目，會載入最新的版本安裝在電腦上的 clr。  
  
 `rclsid`  
 [in]`CLSID`的實作的 coclass [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)介面。 支援的值為 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 [in]`IID`您所要求的介面。 支援的值為 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 [out]傳回的介面指標。  
  
## <a name="requirements"></a>需求  
 **平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **程式庫：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [CorBindToRuntime 函式](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg 函式](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx 函式](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost 函式](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 介面](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [已被取代的 CLR 裝載函式](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
