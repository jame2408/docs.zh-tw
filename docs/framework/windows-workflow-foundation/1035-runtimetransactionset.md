---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510030"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>屬性  
  
|||  
|-|-|  
|ID|1035|  
|關鍵字|WFRuntime|  
|層級|詳細資訊|  
|通道|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>描述  
 表示活動已設定執行階段交易。  
  
## <a name="message"></a>訊息  
 執行階段交易已預先設定活動 '%1'、 DisplayName: '%2'、 InstanceId: '%3'。  執行已隔離到活動 '%4'、 DisplayName: '%5'、 InstanceId: '%6'。  
  
## <a name="details"></a>詳細資料  
  
|資料項目名稱|資料項目型別|描述|  
|--------------------|--------------------|-----------------|  
|活動|xs:string|活動的型別名稱。|  
|DisplayName|xs:string|活動的顯示名稱。|  
|InstanceId|xs:string|活動的執行個體 ID。|  
|IsolatedActivity|xs:string|隔離交易之目標活動的型別名稱。|  
|IsolatedActivityDisplayName|xs:string|隔離交易之目標活動的顯示名稱。|  
|IsolatedActivityInstanceId|xs:string|隔離交易之目標活動的執行個體 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 傳回的字串。|
