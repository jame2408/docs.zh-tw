---
title: 如何：從直線、曲線和形狀建立圖形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 222245fa4b3b593e0a38752a8cb991a12e469698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521852"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>如何：從直線、曲線和形狀建立圖形
若要建立圖，建構<xref:System.Drawing.Drawing2D.GraphicsPath>，然後呼叫方法，例如<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>、 加入路徑中的基本項目。  
  
## <a name="example"></a>範例  
 下列程式碼範例會建立含有圖形的路徑：  
  
-   第一個範例會建立包含單一圖形的路徑。 此圖中所組成的單一弧線。弧線具有-180 度掃掠角度，其預設座標系統中以逆時針算起。  
  
-   第二個範例會建立具有兩個圖形的路徑。 第一個圖是後面接著行弧形。 第二個是後面接著曲線，後面接著一條線的線。 處於開啟狀態，此圖中第一個和第二個為已關閉。  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 先前的範例搭配 Windows Form 使用所設計，以及它們需要<xref:System.Windows.Forms.PaintEventArgs> `e`，這是參數的<xref:System.Windows.Forms.Control.Paint>事件處理常式。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [建構和繪製路徑](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [使用畫筆繪製線條和形狀](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
