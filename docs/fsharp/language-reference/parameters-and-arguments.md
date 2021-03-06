---
title: 參數和引數
description: 深入了解F#定義參數，以及將引數傳遞至函式、 方法和屬性的語言支援。
ms.date: 05/16/2016
ms.openlocfilehash: 08332ad9ab1c1a05f68ba27b2f1513ad0fe7c4d5
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612474"
---
# <a name="parameters-and-arguments"></a>參數和引數

本主題描述針對定義參數，以及將引數傳遞至函式、 方法和屬性的語言支援。 它包含如何傳遞的參考，以及如何定義和使用方法可接受可變數目的引數的相關資訊。

## <a name="parameters-and-arguments"></a>參數和引數

詞彙*參數*用來描述應提供的值的名稱。 詞彙*引數*用於提供每個參數的值。

在 tuple、 局部調用的形式，或兩者的一些組合，可以指定參數。 您可以使用明確的參數名稱傳遞引數。 方法的參數可以指定為選擇性，並指定預設值。

## <a name="parameter-patterns"></a>參數模式

提供給函式和方法的參數在一般情況下，是以空格分隔的模式。 這表示，基本上，任何模式中所述[比對運算式](match-expressions.md)可用參數清單中的函式或成員。

方法通常會使用傳遞引數的 tuple 形式。 這也可達到更清楚的結果從其他.NET 語言的觀點來看，因為 tuple 形式符合.NET 方法中傳遞引數的方式。

局部調用的形式最常搭配使用所建立的函式`let`繫結。

下列虛擬程式碼會示範 tuple 和局部調用引數的範例。

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

結合的表單時，某些引數是在 tuple，而有些則不。

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

其他模式也可用在參數清單中，但如果參數模式不符合所有可能的輸入，可能會有不完整的相符項目在執行階段。 例外狀況`MatchFailureException`引數的值不符合指定的參數清單中的模式時，會產生。 參數模式允許不完全相符的項目時，編譯器會發出警告。 至少一個其他的模式是常用的參數清單和萬用字元模式。 當您只想要忽略所提供的任何引數時，您可以使用在參數清單中的萬用字元模式。 下列程式碼說明如何使用引數清單中的萬用字元模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

萬用字元模式時您不感興趣通常會提供以字串陣列，如下列程式碼所示的命令列引數，可能會很有用，每當您不需要傳入的引數，例如程式的主要進入點。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

有時會用於引數的其他模式是`as`模式和差別聯的集和作用中的模式與相關聯的識別項模式。 您可以使用單一案例的已區分聯集模式，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

輸出如下。

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

作用中的模式有助於進行做為參數，例如，將引數轉換成所需的格式，如下列範例所示：

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

您可以使用`as`模式來儲存為本機值時，相符的值，如下列程式碼所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

偶爾使用的另一種模式是會保留最後一個未命名的提供，做為主體的函式的引數的函式、 lambda 運算式的隱含引數會立即執行模式比對。 其中一個範例就是下列程式碼行。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

此程式碼定義的函式會採用泛型清單，並傳回`true`如果清單是空的、 和`false`否則。 使用這類技術可以讓程式碼更難讀取。

有時候，模式，牽涉到不完整的相符項目很有用，例如，如果您知道您的程式中的清單有三個項目，您可能使用如下所示的模式參數清單中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

有未完成的比對的模式使用適合快速建立原型和其他暫存的用途。 編譯器會發出這類程式碼的警告。 這種模式無法涵蓋所有可能的輸入的一般情況下，因此不適合元件 Api。

## <a name="named-arguments"></a>具名引數

方法的引數可以指定以逗號分隔的引數清單中的位置，或可以將它們傳遞至方法明確地提供的名稱，後面接著等號和要傳入的值。 如果指定藉由提供名稱，它們可以出現在宣告中所使用的不同的順序。

具名引數可讓程式碼更容易讀取和可調整某些類型的 API，例如重新排列方法參數中的變更。

對於方法，只允許具名引數不適用於`let`-繫結函式、 函式值或 lambda 運算式。

下列程式碼範例示範如何使用具名引數。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

在類別建構函式呼叫中，您可以使用類似的具名引數的語法設定類別的屬性的值。 下列範例會顯示此語法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

如需詳細資訊，請參閱 <<c0> [ 建構函式 (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。</c0>

## <a name="optional-parameters"></a>選擇性參數

您可以使用參數名稱前面的問號，以指定方法的選擇性參數。 選擇性參數會被解譯為F#選項類型，因此您可以按照一般方式，查詢選項類型，使用查詢`match`運算式`Some`並`None`。 只有在成員，使用所建立的函式上不允許選擇性參數`let`繫結。

您可以現有選擇性將值傳遞至方法的參數名稱，例如`?arg=None`或是`?arg=Some(3)`或`?arg=arg`。 建置方法，會將傳遞至另一種方法的選擇性引數時，這非常有用。

您也可以使用函式`defaultArg`，可設定預設值是選擇性的引數。 `defaultArg`函數接受選擇性的參數做為第一個引數和預設值為第二個。

下列範例說明如何使用選擇性參數。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

輸出如下。

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

目的C#，您可以使用屬性的 Visual Basic interop`[<Optional; DefaultParameterValue<(...)>]`在F#，如此一來，呼叫端將會看到引數為選擇性。 這相當於定義引數為選擇性的C#示`MyMethod(int i = 3)`。

```fsharp
open System
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

提供做為引數的值`DefaultParameterValue`必須符合的型別參數，也就是下列不允許的：

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

在此情況下，編譯器會產生警告，並會完全忽略這兩個屬性。 請注意，預設值`null`必須是型別-註解，否則，編譯器會推斷類型不正確，也就是`[<Optional; DefaultParameterValue(null:obj)>] o:obj`。

## <a name="passing-by-reference"></a>傳址方式傳遞

傳遞F#所參考的值包含[byref](byrefs.md)，這是 managed 的指標類型。 若要使用哪種類型時，如下所示的指引：

* 使用`inref<'T>`如果您只需要讀取的指標。
* 使用`outref<'T>`如果您只需要撰寫的指標。
* 使用`byref<'T>`如果您需要從讀取和寫入的指標。

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

因為參數是指標，且值是可變動，仍會保留值的任何變更之後執行的函式。

您可以做為傳回值使用 tuple，來儲存任何`out`.NET 程式庫方法中的參數。 或者，您可以將視為`out`參數做為`byref`參數。 下列程式碼範例說明這兩種方式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>參數陣列

偶爾也會需要定義任意數目的異質的型別參數的函式。 它不會實際建立所有可能多載的方法來處理所有可用的類型。 .NET 實作提供這類方法，透過參數陣列功能的支援。 採用在其簽章的參數陣列的方法可供任意數目的參數使用。 參數會放入陣列。 陣列元素的類型會決定可以傳遞至函式的參數型別。 如果您定義的參數陣列`System.Object`做為項目類型，則用戶端程式碼可以傳遞任何類型的值。

在F#，只能在方法中定義的參數陣列。 它們不能在獨立函式或模組中定義的函式。

您可以使用定義的參數陣列`ParamArray`屬性。 `ParamArray`屬性只能套用至最後一個參數。

下列程式碼說明這兩個呼叫的.NET 方法，會使用參數陣列和中的型別定義F#具有採用參數陣列的方法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

當執行在專案中，先前的程式碼的輸出如下所示：

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>另請參閱

- [成員](members/index.md)