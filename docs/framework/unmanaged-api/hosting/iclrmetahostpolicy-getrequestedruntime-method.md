---
title: "ICLRMetaHostPolicy::GetRequestedRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy.GetRequestedRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57e5efc604568aea0a6edef5cc57f83fb99eb561
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="d903c-102">ICLRMetaHostPolicy::GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="d903c-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>
<span data-ttu-id="d903c-103">提供 Common Language Runtime (CLR) 慣用版本的介面，這是根據裝載原則、Managed 組件、版本字串和組態資料流。</span><span class="sxs-lookup"><span data-stu-id="d903c-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="d903c-104">這個方法實際上不會載入或啟用 CLR，而只會傳回[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)代表原則結果的介面。</span><span class="sxs-lookup"><span data-stu-id="d903c-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="d903c-105">這個方法會取代[GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)， [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)， [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)， [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)，和[GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d903c-105">This method supersedes the [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d903c-106">語法</span><span class="sxs-lookup"><span data-stu-id="d903c-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntime(  
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,  
    [in]  LPCWSTR pwzBinary,  
    [in]  IStream *pCfgStream,  
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,  
    [in, out]  DWORD *pcchVersion,  
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,  
    [in, out]  DWORD *pcchImageVersion,  
    [out] DWORD *pdwConfigFlags,  
    [in]  REFIID  riid  
    [out, iid_is(riid), retval] LPVOID *ppRuntime);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d903c-107">參數</span><span class="sxs-lookup"><span data-stu-id="d903c-107">Parameters</span></span>  
  
|<span data-ttu-id="d903c-108">名稱</span><span class="sxs-lookup"><span data-stu-id="d903c-108">Name</span></span>|<span data-ttu-id="d903c-109">說明</span><span class="sxs-lookup"><span data-stu-id="d903c-109">Description</span></span>|  
|----------|-----------------|  
|`dwPolicyFlags`|<span data-ttu-id="d903c-110">[in] 必要項。</span><span class="sxs-lookup"><span data-stu-id="d903c-110">[in] Required.</span></span> <span data-ttu-id="d903c-111">指定的成員[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)列舉型別，代表繫結原則，以及任何數目的修飾詞。</span><span class="sxs-lookup"><span data-stu-id="d903c-111">Specifies a member of the [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="d903c-112">目前可用的唯一原則是[METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="d903c-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="d903c-113">修飾詞包含[METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)， [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)，和[METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="d903c-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span>|  
|`pwzBinary`|<span data-ttu-id="d903c-114">[in] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-114">[in] Optional.</span></span> <span data-ttu-id="d903c-115">指定組件檔路徑。</span><span class="sxs-lookup"><span data-stu-id="d903c-115">Specifies the assembly file path.</span></span>|  
|`pCfgStream`|<span data-ttu-id="d903c-116">[in] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-116">[in] Optional.</span></span> <span data-ttu-id="d903c-117">以 <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType> 指定組態檔。</span><span class="sxs-lookup"><span data-stu-id="d903c-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|  
|`pwzVersion`|<span data-ttu-id="d903c-118">[in, out] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-118">[in, out] Optional.</span></span> <span data-ttu-id="d903c-119">指定或傳回要載入的慣用 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="d903c-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|  
|`pcchVersion`|<span data-ttu-id="d903c-120">[in, out] 必要項。</span><span class="sxs-lookup"><span data-stu-id="d903c-120">[in, out] Required.</span></span> <span data-ttu-id="d903c-121">指定 `pwzVersion` 做為輸入的預期大小，以避免緩衝區滿溢。</span><span class="sxs-lookup"><span data-stu-id="d903c-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="d903c-122">如果 `pwzVersion` 為 null，`pcchVersion` 包含 `GetRequestedRuntime` 傳回時 `pwzVersion` 的預期大小，以便預先配置，否則 `pcchVersion` 包含要寫入 `pwzVersion` 的字元數目。</span><span class="sxs-lookup"><span data-stu-id="d903c-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|  
|`pwzImageVersion`|<span data-ttu-id="d903c-123">[out] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-123">[out] Optional.</span></span> <span data-ttu-id="d903c-124">當`GetRequestedRuntime`傳回時，包含 CLR 版本對應到[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)傳回的介面。</span><span class="sxs-lookup"><span data-stu-id="d903c-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that is returned.</span></span>|  
|`pcchImageVersion`|<span data-ttu-id="d903c-125">[in, out] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-125">[in, out] Optional.</span></span> <span data-ttu-id="d903c-126">指定 `pwzImageVersion` 做為輸入的大小，以避免緩衝區滿溢。</span><span class="sxs-lookup"><span data-stu-id="d903c-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="d903c-127">如果 `pwzImageVersion` 為 null， `pcchImageVersion` 包含 `GetRequestedRuntime` 傳回時的 `pwzImageVersion` 必要大小，以便預先配置。</span><span class="sxs-lookup"><span data-stu-id="d903c-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|  
|`pdwConfigFlags`|<span data-ttu-id="d903c-128">[out] 選用。</span><span class="sxs-lookup"><span data-stu-id="d903c-128">[out] Optional.</span></span> <span data-ttu-id="d903c-129">如果`GetRequestedRuntime`繫結過程中，使用組態檔，當它傳回時，`pdwConfigFlags`包含[METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)值，指出是否[\<啟動 >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)項目具有`useLegacyV2RuntimeActivationPolicy`屬性集和屬性的值。</span><span class="sxs-lookup"><span data-stu-id="d903c-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="d903c-130">套用[METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)遮罩至`pdwConfigFlags`以取得的值與`useLegacyV2RuntimeActivationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="d903c-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
|`riid`|<span data-ttu-id="d903c-131">[in]指定所要求的介面識別碼 IID_ICLRRuntimeInfo [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)介面。</span><span class="sxs-lookup"><span data-stu-id="d903c-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|  
|`ppRuntime`|<span data-ttu-id="d903c-132">[out]當`GetRequestedRuntime`傳回時，包含對應的指標[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)介面。</span><span class="sxs-lookup"><span data-stu-id="d903c-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d903c-133">備註</span><span class="sxs-lookup"><span data-stu-id="d903c-133">Remarks</span></span>  
 <span data-ttu-id="d903c-134">當這個方法成功時，它的副作用是會合併其他旗標與傳回之執行階段介面的目前預設啟動旗標，並且只在 `<configuration><runtime>` 區段內有一或多個下列項目存在於組態資料流時：</span><span class="sxs-lookup"><span data-stu-id="d903c-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>  
  
-   <span data-ttu-id="d903c-135">`<gcServer enabled="true"/>` 會導致設定 `STARTUP_SERVER_GC`。</span><span class="sxs-lookup"><span data-stu-id="d903c-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>  
  
-   <span data-ttu-id="d903c-136">`<etwEnable enabled="true"/>` 會導致設定 `STARTUP_ETW`。</span><span class="sxs-lookup"><span data-stu-id="d903c-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>  
  
-   <span data-ttu-id="d903c-137">`<appDomainResourceMonitoring enabled="true"/>` 會導致設定 `STARTUP_ARM`。</span><span class="sxs-lookup"><span data-stu-id="d903c-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>  
  
 <span data-ttu-id="d903c-138">產生的預設 `STARTUP_FLAGS` 值是從上述清單設定之值與預設啟動旗標值的位元 OR 合併。</span><span class="sxs-lookup"><span data-stu-id="d903c-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d903c-139">傳回值</span><span class="sxs-lookup"><span data-stu-id="d903c-139">Return Value</span></span>  
 <span data-ttu-id="d903c-140">這個方法會傳回下列特定的 HRESULT 以及 HRESULT 錯誤，以指出方法失敗。</span><span class="sxs-lookup"><span data-stu-id="d903c-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d903c-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d903c-141">HRESULT</span></span>|<span data-ttu-id="d903c-142">描述</span><span class="sxs-lookup"><span data-stu-id="d903c-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d903c-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="d903c-143">S_OK</span></span>|<span data-ttu-id="d903c-144">已成功完成命令。</span><span class="sxs-lookup"><span data-stu-id="d903c-144">The method completed successfully.</span></span>|  
|<span data-ttu-id="d903c-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d903c-145">E_POINTER</span></span>|<span data-ttu-id="d903c-146">`pwzVersion` 不是 null 且 `pcchVersion` 是 null。</span><span class="sxs-lookup"><span data-stu-id="d903c-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="d903c-147">-或-</span><span class="sxs-lookup"><span data-stu-id="d903c-147">-or-</span></span><br /><br /> <span data-ttu-id="d903c-148">`pwzImageVersion` 不是 null 且 `pcchImageVersion` 是 null。</span><span class="sxs-lookup"><span data-stu-id="d903c-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|  
|<span data-ttu-id="d903c-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d903c-149">E_INVALIDARG</span></span>|<span data-ttu-id="d903c-150">`dwPolicyFlags` 未指定 `METAHOST_POLICY_HIGHCOMPAT`。</span><span class="sxs-lookup"><span data-stu-id="d903c-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|  
|<span data-ttu-id="d903c-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d903c-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d903c-152">配置給 `pwzVerison` 的記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="d903c-152">The memory allocated to `pwzVerison` is inadequate.</span></span><br /><br /> <span data-ttu-id="d903c-153">-或-</span><span class="sxs-lookup"><span data-stu-id="d903c-153">-or-</span></span><br /><br /> <span data-ttu-id="d903c-154">配置給 `pwzImageVerison` 的記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="d903c-154">The memory allocated to `pwzImageVerison` is inadequate.</span></span>|  
|<span data-ttu-id="d903c-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="d903c-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="d903c-156">`dwPolicyFlags` 包括 METAHOST_POLICY_APPLY_UPGRADE_POLICY，且 `pwzVersion` 和 `pcchVersion` 都是 null。</span><span class="sxs-lookup"><span data-stu-id="d903c-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d903c-157">需求</span><span class="sxs-lookup"><span data-stu-id="d903c-157">Requirements</span></span>  
 <span data-ttu-id="d903c-158">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d903c-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d903c-159">**標頭：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d903c-159">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d903c-160">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="d903c-160">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d903c-161">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d903c-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d903c-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d903c-162">See Also</span></span>  
 [<span data-ttu-id="d903c-163">ICLRMetaHostPolicy 介面</span><span class="sxs-lookup"><span data-stu-id="d903c-163">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 [<span data-ttu-id="d903c-164">在.NET Framework 4 和 4.5 加入的 CLR 裝載介面</span><span class="sxs-lookup"><span data-stu-id="d903c-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="d903c-165">裝載介面</span><span class="sxs-lookup"><span data-stu-id="d903c-165">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d903c-166">裝載</span><span class="sxs-lookup"><span data-stu-id="d903c-166">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)