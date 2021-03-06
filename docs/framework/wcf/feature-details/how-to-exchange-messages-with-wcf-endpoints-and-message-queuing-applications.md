---
title: HOW TO：與 WCF 端點和訊息佇列應用程式交換訊息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 807a34ac50ea317ace42ec12eddcd9ec7cf3736b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491075"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>HOW TO：與 WCF 端點和訊息佇列應用程式交換訊息
您可以將現有訊息佇列 (MSMQ) 應用程式與 Windows Communication Foundation (WCF) 應用程式整合，使用 MSMQ 整合繫結，將 MSMQ 訊息，與 WCF 訊息。 這可讓您呼叫 MSMQ 接收者應用程式從 WCF 用戶端，以及從 MSMQ 傳送者應用程式呼叫 WCF 服務。  
  
 在本節中，我們會說明如何使用<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>（1） 的 WCF 用戶端與使用 System.Messaging 和 （2) MSMQ 應用程式用戶端和 WCF 服務所撰寫的 MSMQ 應用程式服務之間的佇列通訊。  
  
 如需示範如何從 WCF 用戶端呼叫 MSMQ 接收者應用程式的完整範例，請參閱[Windows Communication Foundation 至訊息佇列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)範例。  
  
 如需示範如何從 MSMQ 用戶端呼叫 WCF 服務的完整範例，請參閱[Message Queuing，將 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)範例。  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>若要從 MSMQ 用戶端建立可接收訊息的 WCF 服務  
  
1.  定義這個介面會定義服務合約的 WCF 服務會接收來自 MSMQ 傳送者應用程式中，佇列的訊息，如下列範例程式碼所示。  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  實作介面並將 <xref:System.ServiceModel.ServiceBehaviorAttribute> 屬性套用至類別，如下列範例程式碼所示。  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  建立會指定 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 的組態檔。  
  
  
  
4.  產生可使用設定繫結的 <xref:System.ServiceModel.ServiceHost> 物件。  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>若要建立可將訊息傳送至 MSMQ 接收者應用程式的 WCF 用戶端  
  
1.  定義這個介面會定義傳送佇列訊息至 MSMQ 接收者，WCF 用戶端的服務合約，如下列範例程式碼所示。  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  定義 WCF 用戶端用來呼叫 MSMQ 接收者的用戶端類別。  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  建立會指定 MsmqIntegrationBinding 繫結使用的組態。  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  建立用戶端類別的執行個體，並呼叫訊息接收服務所定義的方法。  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>另請參閱  
 [佇列概觀](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [如何：與 WCF 端點交換佇列訊息](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [Windows Communication Foundation 至訊息佇列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [安裝訊息佇列 (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [訊息佇列至 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [訊息佇列上的訊息安全性](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
