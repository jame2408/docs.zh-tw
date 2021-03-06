---
title: 如何：將控制項加入至 Windows Form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 1b803a93f865eaa4db6751187213c4bb01d2a5ee
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213088"
---
# <a name="how-to-add-controls-to-windows-forms"></a>如何：將控制項加入至 Windows Form
大部分的表單都設計成將控制項加入表單的介面，來定義使用者介面 (UI)。 A*控制*是用來顯示資訊，或接受使用者輸入表單上的元件。 如需控制項的詳細資訊，請參閱[Windows Forms 控制項](../../../../docs/framework/winforms/controls/index.md)。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-draw-a-control-on-a-form"></a>若要繪製在表單上控制項  
  
1.  開啟表單。 如需詳細資訊，請參閱 <<c0> [ 如何： 顯示 Windows Form 設計工具中](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。  
  
2.  在 **工具箱**，按一下您想要新增至表單的控制項。  
  
3.  在表單中，按一下您想要找出，控制項的左上角並拖曳至要放置控制項的右下角的位置。  
  
     控制項會加入至表單的指定的位置和大小。  
  
    > [!NOTE]
    >  每個控制項已定義的預設大小。 您可以將控制項加入您的表單控制項的預設大小從拖曳**工具箱**至表單。  
  
### <a name="to-drag-a-control-to-a-form"></a>若要將控制項拖曳至表單  
  
1.  開啟表單。 如需詳細資訊，請參閱 <<c0> [ 如何： 顯示 Windows Form 設計工具中](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。  
  
2.  在 **工具箱**，按一下您想要並將它拖曳至表單的控制項。  
  
     控制項會加入至指定的位置，以預設大小的表單。  
  
    > [!NOTE]
    >  您可以按兩下中的控制項**工具箱**將它新增至其預設大小 中表單的左上角。  
  
     您可以也將控制項以動態方式加入表單在執行階段。 在下列程式碼範例中，<xref:System.Windows.Forms.TextBox>控制項將會加入至表單時<xref:System.Windows.Forms.Button>按一下控制項時。  
  
    > [!NOTE]
    >  下列程序需要有的表單** 按鈕**控制項， `Button1`、 已放在其上。  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>若要以程式設計方式將控制項加入表單  
  
1.  在方法中處理按鈕的`Click`事件，在您的表單類別中，插入程式碼如下所示將參考加入至您的控制項變數，將控制項的`Location`，並加入控制項。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  您也可以加入程式碼以初始化控制項的其他屬性。  
  
    > [!IMPORTANT]
    >  您可能會公開本機電腦透過網路的安全性風險，藉由參考惡意`UserControl`。 這只會在惡意人士建立破壞性的自訂控制項，且您不小心將它新增至您的專案的情況下需要考量。  
  
## <a name="see-also"></a>另請參閱  
 [Windows Forms 控制項](../../../../docs/framework/winforms/controls/index.md)  
 [排列 Windows Forms 上的控制項](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [操作說明：重新調整 Windows Forms 上控制項的大小](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [操作說明：設定由 Windows Forms 控制項所顯示的文字](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [在 Windows Forms 上使用的控制項](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
