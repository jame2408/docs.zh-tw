---
title: '&lt;BackupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 1a6a7ac42b379dd8fb2ba80cf6a3a38998c26a59
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146546"
---
# <a name="ltbackuplistgt"></a>&lt;BackupList&gt;
代表定義備份清單會列舉一組您希望路由服務在無法找到主要端點時使用的端點組態區段。 如果清單中的第一個端點關閉，路由服務將自動容錯移轉至清單中的下一個端點。  如此可提供您快速提升應用程式可靠性的方式，而不需教導用戶端應用程式如何處理複雜的模式以及部署所有服務的位置。  
  
 \<system.serviceModel>  
\<路由 >  
\<backupLists >  
\<a d d >  
  
## <a name="syntax"></a>語法  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|name|字串，指定用於識別這個端點清單的名稱。|  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|備份端點的清單。|  
  
## <a name="remarks"></a>備註  
 這個區段包含依順序排列的端點集合，訊息會在傳送至主要端點期間發生通訊例外狀況事件時，傳輸至這些端點。  
  
 如果傳送至主要端點列於`endpointName`的屬性[\<新增 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md)因通訊例外狀況，路由服務會嘗試將訊息傳送至第一個端點，在此組態區段。 如果這項作業同樣因為通訊例外狀況而失敗，則路由服務將嘗試傳送訊息至這個區段中包含的下一個訊息，直到嘗試成功、傳回通訊例外狀況以外的失敗，或是集合中所有端點都傳回失敗為止。  
  
 在下列範例中，如果傳送至名為 「 目的地 」 的主要端點傳回通訊例外狀況，則服務將嘗試傳送訊息至"alternateServiceQueue"。 如果這項嘗試同樣傳回通訊例外狀況，則路由服務將嘗試傳送訊息至集合中的下一個端點。  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
