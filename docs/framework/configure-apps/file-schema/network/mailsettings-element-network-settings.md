---
title: '&lt;mailSettings&gt;項目 （網路設定）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 5c7b4d8fae2774fe8e52718fbce91e4bc193c124
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198428"
---
# <a name="ltmailsettingsgt-element-network-settings"></a>&lt;mailSettings&gt;項目 （網路設定）
設定郵件傳送選項。  

\<configuration>  
\<system.net>  
\<mailSettings>  
  
## <a name="syntax"></a>語法  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子元素  
  
|屬性|描述|  
|---------------|-----------------|  
|[\<smtp > 項目 （網路設定）](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|設定簡易郵件傳輸通訊協定選項。|  
  
### <a name="parent-elements"></a>父項目  
  
|**目**|**描述**|  
|-----------------|---------------------|  
|[\<system.Net> 項目 (網路設定)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|包含會指定 .NET Framework 如何連接至網路的設定。|  
  
## <a name="example"></a>範例  
 下列範例會指定適當的 SMTP 參數，使用預設網路認證傳送電子郵件。  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
- <xref:System.Net.Mail.SmtpClient>  
- [網路設定結構描述](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
