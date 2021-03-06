---
title: 如何：Windows Forms DataGridView 儲存格中的主控制項
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 29ffcc205d8175551aee5184cf44306fa5d3b5a0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799810"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>如何：Windows Forms DataGridView 儲存格中的主控制項
<xref:System.Windows.Forms.DataGridView> 控制項提供許多資料行類型，讓使用者以各種不同的方式輸入和編輯值。 如果這些資料行類型不符合您輸入資料的需求，則您仍可用裝載您所選擇的控制項之儲存格來建立自己的資料行類型。 若要這樣做，您必須定義衍生自 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewCell> 的類別。 您也必須定義衍生自 <xref:System.Windows.Forms.Control> 的類別，並實作 <xref:System.Windows.Forms.IDataGridViewEditingControl> 介面。  
  
 下列程式碼範例示範如何建立行事曆資料行。 這個資料行的儲存格會在一般文字方塊中的儲存格顯示日期，但是當使用者編輯儲存格時，<xref:System.Windows.Forms.DateTimePicker> 控制項就會出現。 若要避免再次實作文字方塊顯示功能，則 `CalendarCell` 類別要衍生自 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 類別，而不是直接繼承 <xref:System.Windows.Forms.DataGridViewCell> 類別。  
  
> [!NOTE]
>  當您從 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 衍生並將新屬性加入衍生類別時，請務必覆寫 `Clone` 方法，以便於複製作業期間複製新屬性。 您也應該呼叫基底類別的 `Clone` 方法，以便將基底類別的屬性複製到新的儲存格或資料行。  
  
## <a name="example"></a>範例  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 下列範例需要：  
  
-   System 和 System.Windows.Forms 組件的參考。  
  
 Visual Basic 或 Visual C# 建置此範例從命令列的相關資訊，請參閱[從命令列建置](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或是[命令列使用 csc.exe 建置](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 您也可以將程式碼貼入新的專案，以建置此範例的 Visual Studio。  另請參閱[如何：使用 Visual Studio 編譯及執行完整的 Windows Forms 程式碼範例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [自訂 Windows Forms DataGridView 控制項](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [DataGridView 控制項架構](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Windows Forms DataGridView 控制項中的資料行類型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
