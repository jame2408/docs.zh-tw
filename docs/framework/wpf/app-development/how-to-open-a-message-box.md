---
title: "如何： 開啟訊息方塊"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 302a3cd34d90d47e38af1bbeaadca7e777a26395
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="a9e1a-102">如何： 開啟訊息方塊</span><span class="sxs-lookup"><span data-stu-id="a9e1a-102">How to: Open a Message Box</span></span>
<span data-ttu-id="a9e1a-103">這個範例示範如何開啟訊息方塊。</span><span class="sxs-lookup"><span data-stu-id="a9e1a-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9e1a-104">範例</span><span class="sxs-lookup"><span data-stu-id="a9e1a-104">Example</span></span>  
 <span data-ttu-id="a9e1a-105">訊息方塊是預先製作好強制回應對話方塊，可對使用者顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="a9e1a-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="a9e1a-106">藉由呼叫靜態開啟訊息方塊<xref:System.Windows.MessageBox.Show%2A>方法<xref:System.Windows.MessageBox>類別。</span><span class="sxs-lookup"><span data-stu-id="a9e1a-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="a9e1a-107">當<xref:System.Windows.MessageBox.Show%2A>是呼叫，將訊息傳遞使用字串參數。</span><span class="sxs-lookup"><span data-stu-id="a9e1a-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="a9e1a-108">數個多載的<xref:System.Windows.MessageBox.Show%2A>讓您設定訊息方塊出現的方式 (請參閱<xref:System.Windows.MessageBox>)。</span><span class="sxs-lookup"><span data-stu-id="a9e1a-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="a9e1a-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a9e1a-109">See Also</span></span>  
 [<span data-ttu-id="a9e1a-110">MessageBox 範例</span><span class="sxs-lookup"><span data-stu-id="a9e1a-110">MessageBox Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160023)