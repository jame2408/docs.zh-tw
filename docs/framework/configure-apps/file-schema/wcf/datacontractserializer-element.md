---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: c79c8e8db2a4ea4526000bcbe336d1e664f9c4c2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150951"
---
# <a name="ltdatacontractserializergt"></a>&lt;DataContractSerializer&gt;
包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的組態資料。 這個項目會出現在兩個不同的階層架構中。 其中一個列於接下來的＜結構描述階層架構＞一節，另一個則列於＜備註＞一節中。  
  
 \<system.ServiceModel>  
\<行為 >  
\<serviceBehaviors>  
\<行為 >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>語法  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|元素|描述|  
|-------------|-----------------|  
|ignoreExtensionDataObject|布林值，該值會指定當端點序列化或還原序列化時，是否略過端點所提供的資料。 此屬性只能在 `<dataContractSerializer>` 項目下的 `<behavior>` 設定。|  
|maxItemsInObjectGraph|整數，指定要序列化或還原序列化的項目數上限。 此屬性為 65536。|  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<行為 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|服務行為之設定的集合。|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|代表 <xref:System.Runtime.Serialization> 命名空間區段的根項目，而且包含用來設定 <xref:System.Runtime.Serialization.DataContractSerializer> 選項的項目。|  
  
## <a name="remarks"></a>備註  
 本主題簡介所述，這會是第二個階層，在其中\<X509Extension > 項目，就會發生。  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 如需有關已知型別的詳細資訊，請參閱 <xref:System.Runtime.Serialization.DataContractSerializer>。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [資料合約已知類型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [資料傳輸與序列化](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
