---
title: 如何：在 TableLayoutPanel 控制項中對齊和縮放控制項
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: 06e152058337955164bd526e20e023d759340f01
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504149"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控制項中對齊和縮放控制項
您可以對齊和縮放控制項<xref:System.Windows.Forms.TableLayoutPanel>具有<xref:System.Windows.Forms.Control.Anchor%2A>和<xref:System.Windows.Forms.Control.Dock%2A>屬性。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-align-and-stretch-a-control"></a>若要對齊和縮放控制項  
  
1.  拖曳<xref:System.Windows.Forms.TableLayoutPanel>控制項從**工具箱**拖曳至表單。  
  
2.  拖曳<xref:System.Windows.Forms.Button>控制項從**工具箱**的左上方儲存格中<xref:System.Windows.Forms.TableLayoutPanel>控制項。 <xref:System.Windows.Forms.Button>控制項在儲存格中置中對齊。  
  
3.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Anchor%2A>屬性設`Left,Right`。 <xref:System.Windows.Forms.Button>控制兩端之間自動縮放以符合儲存格的寬度。  
  
4.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Anchor%2A>屬性設`Top,Bottom`。 <xref:System.Windows.Forms.Button>控制兩端之間自動縮放以符合資料格的高度。  
  
5.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Dock%2A>屬性設<xref:System.Windows.Forms.DockStyle.Fill>。 <xref:System.Windows.Forms.Button>展開以填滿儲存格的控制項。  
  
6.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Dock%2A>屬性設<xref:System.Windows.Forms.DockStyle.None>。 <xref:System.Windows.Forms.Button>控制項傳回至其原始大小，並將移至儲存格的左上角。 **Windows Form 設計工具**已設定<xref:System.Windows.Forms.Control.Anchor%2A>屬性設`Top, Left`。  
  
7.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Anchor%2A>屬性設`Bottom,Right`。 <xref:System.Windows.Forms.Button>控制項移到儲存格右下角。  
  
8.  設定的值<xref:System.Windows.Forms.Button>控制項的<xref:System.Windows.Forms.Control.Anchor%2A>屬性設<xref:System.Windows.Forms.AnchorStyles.None>。 <xref:System.Windows.Forms.Button>控制項移到儲存格的中央。  
  
## <a name="see-also"></a>另請參閱  
 [TableLayoutPanel 控制項](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
