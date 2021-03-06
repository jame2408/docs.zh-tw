---
title: 如何：刪除或隱藏 Windows Form DataGrid 控制項中的資料行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 6541ffff1149e5df13c43ee392ffa8b221c8407d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534550"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>如何：刪除或隱藏 Windows Form DataGrid 控制項中的資料行
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控制項會取代 <xref:System.Windows.Forms.DataGrid> 控制項並加入其他功能，不過您也可以選擇保留 <xref:System.Windows.Forms.DataGrid> 控制項，以提供回溯相容性及未來使用。 如需詳細資訊，請參閱 [Windows Forms DataGridView 和 DataGrid 控制項之間的差異](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 您可以透過程式設計方式刪除或隱藏 Windows Form 中的資料行<xref:System.Windows.Forms.DataGrid>控制項使用的屬性和方法的<xref:System.Windows.Forms.GridColumnStylesCollection>和<xref:System.Windows.Forms.DataGridColumnStyle>物件 (的成員<xref:System.Windows.Forms.DataGridTableStyle>類別)。  
  
 已刪除或隱藏的資料行仍會存在於方格繫結，而您仍然可以透過程式設計方式存取資料來源。 它們不再只顯示在資料格中。  
  
> [!NOTE]
>  如果您的應用程式不會存取特定資料行的資料，而且您不要它們顯示在資料格中，則它不可能不需要將它們在第一次包含在資料來源。  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>若要以程式設計方式在 DataGrid 中刪除資料行  
  
1.  在您的表單宣告區域中，宣告的新執行個體<xref:System.Windows.Forms.DataGridTableStyle>類別。  
  
2.  設定<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType>屬性至您想要套用樣式的資料來源中的資料表。 下列範例會使用<xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>屬性，它會假設已設定。  
  
3.  加入新<xref:System.Windows.Forms.DataGridTableStyle>datagrid 的資料表樣式集合的物件。  
  
4.  呼叫<xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A>方法<xref:System.Windows.Forms.DataGrid>的<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>集合，指定要刪除的資料行的資料行索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>若要以程式設計方式隱藏在資料格中的資料行  
  
1.  在您的表單宣告區域中，宣告的新執行個體<xref:System.Windows.Forms.DataGridTableStyle>類別。  
  
2.  設定<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>屬性<xref:System.Windows.Forms.DataGridTableStyle>至您想要套用樣式的資料來源中的資料表。 下列程式碼範例使用<xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>屬性，它會假設已設定。  
  
3.  加入新<xref:System.Windows.Forms.DataGridTableStyle>datagrid 的資料表樣式集合的物件。  
  
4.  隱藏資料行，藉由設定其`Width`屬性設為 0，指定要隱藏的資料行的資料行索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>另請參閱  
 [操作說明：在執行階段時變更 Windows Forms DataGrid 控制項中顯示的資料](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [操作說明：將資料表和資料行新增至 Windows Forms DataGrid 控制項](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
