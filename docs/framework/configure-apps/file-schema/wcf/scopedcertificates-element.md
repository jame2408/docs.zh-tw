---
title: '&lt;scopedCertificates&gt; 項目'
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 6f2acd1078090f7680f1909d68afbcaa09d080fd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150717"
---
# <a name="ltscopedcertificatesgt-element"></a>&lt;scopedCertificates&gt; 項目
表示特定服務 (範圍服務) 為驗證所提供之 X.509 憑證的集合。 這個集合通常用來指定聯合案例中安全性權杖服務的服務憑證。  
  
 \<system.ServiceModel>  
\<行為 >  
endpointBehaviors 區段  
\<行為 >  
\<clientCredentials>  
\<v >  
\<scopedCertificates > 項目  
\<新增 > 項目\<scopedCertificates >  
  
## <a name="syntax"></a>語法  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|將 X.509 憑證加入至範圍憑證的集合。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<v >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|指定對用戶端驗證服務時所使用的憑證。|  
  
## <a name="remarks"></a>備註  
 這個集合可讓用戶端根據與其進行通訊之服務的 URL 設定要使用的服務憑證。 在用戶端可以與多重服務 (終端服務以及中繼安全性權杖服務) 進行通訊的已核發權杖情況中，這個屬性特別有用。 對於使用以憑證為基礎之訊息安全性的繫結，這個憑證會用來加密傳送給服務的訊息，而且預期會被服務用來簽署對用戶端的回覆。  
  
 如果繫結需要服務的憑證，但是在 ScopedCertificates 中找不到服務 URL 的專屬憑證，則會使用預設的憑證。  
  
 如需詳細資訊，請參閱的 < 範圍憑證 > 一節[How to:建立聯合用戶端](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)。  
  
## <a name="example"></a>範例  
 下列範例會指定網域名稱與端點通訊時要使用用戶端的服務憑證 `http://www.contoso.com` 透過 HTTP 通訊協定。  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [使用憑證](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [如何：建立聯合用戶端](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [保護用戶端安全](../../../../../docs/framework/wcf/securing-clients.md)  
 [保護服務和用戶端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
