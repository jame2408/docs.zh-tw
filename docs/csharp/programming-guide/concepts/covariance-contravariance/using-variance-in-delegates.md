---
title: 在委派中使用變異數 (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 5be4f786d2e1b8a0ead3fd58fe056e188faa916a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501720"
---
# <a name="using-variance-in-delegates-c"></a>在委派中使用變異數 (C#)
當您將方法指派給委派時，「共變數」和「反變數」可讓您彈性地比對委派類型和方法簽章。 共變數允許某個方法的傳回型別與定義於委派中的傳回型別相比，其衍生程度較大。 反變數允許某個方法的參數類型與委派類型中的參數類型相比，其衍生程度較小。  
  
## <a name="example-1-covariance"></a>範例 1︰共變數  
  
### <a name="description"></a>描述  
 此範例示範如何搭配其傳回型別衍生自委派簽章中傳回型別的方法使用委派。 `DogsHandler` 所傳回的資料類型是 `Dogs` 類型，該類型衍生自定義於委派中的 `Mammals` 類型。  
  
### <a name="code"></a>程式碼  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a>範例 2：反變數  
  
### <a name="description"></a>描述  
 此範例示範如何搭配其參數類型為委派簽章參數類型之基底類型的方法使用委派。 透過反變數，您可以使用一個事件處理常式，而不是不同的處理常式。 例如，您可以建立一個事件處理常式，該事件處理常式接受 `EventArgs` 輸入參數，並使用它來搭配將 `MouseEventArgs` 類型作為參數傳送的 `Button.MouseClick` 事件，以及搭配傳送 `KeyEventArgs` 參數的 `TextBox.KeyDown` 事件。  
  
### <a name="code"></a>程式碼  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a>請參閱

- [委派中的差異 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
- [針對 Func 與 Action 泛型委派使用變異數 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
