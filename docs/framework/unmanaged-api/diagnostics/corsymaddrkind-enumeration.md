---
title: CorSymAddrKind 列舉
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98cf49714829b4b2f80e0240c2ebde7fa6c280e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425401"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 列舉
指出記憶體位址的類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>成員  
  
|成員|描述|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|表示 Microsoft intermediate language (MSIL) 本機變數或參數索引。|  
|`ADDR_NATIVE_RVA`|表示有相對虛擬位址至模組。|  
|`ADDR_NATIVE_REGISTER`|表示 CPU 暫存器。|  
|`ADDR_NATIVE_REGREL`|表示第一個位址是暫存器，而且第二個位址是位移。|  
|`ADDR_NATIVE_OFFSET`|表示基底地址的位移。|  
|`ADDR_NATIVE_REGREG`|表示第一個位址就是低部分暫存器，且第二個位址的高部分。|  
|`ADDR_NATIVE_REGSTK`|表示第一個位址就是暫存器的低部分、 第二個是高部分，和第三個是位移。|  
|`ADDR_NATIVE_STKREG`|表示第一個位址是暫存器、 第二個是位移，和第三個是暫存器的高部分。|  
|`ADDR_BITFIELD`|表示第一個位址就是欄位的開頭，而且第二個位址是欄位長度。|  
|`ADDR_NATIVE_ISECTOFFSET`|表示第一個位址是區段，而且第二個位址是位移。|  
  
## <a name="requirements"></a>需求  
 **標頭：** 於 CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另請參閱  
 [診斷符號存放區列舉](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
