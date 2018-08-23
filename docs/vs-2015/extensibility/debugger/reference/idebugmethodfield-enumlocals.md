---
title: IDebugMethodField::EnumLocals | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMethodField::EnumLocals
helpviewer_keywords:
- IDebugMethodField::EnumLocals method
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 061d6dccb21bb94871aeed2ac1e20c345a6bf3f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666802"
---
# <a name="idebugmethodfieldenumlocals"></a>IDebugMethodField::EnumLocals
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugMethodField::EnumLocals](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmethodfield-enumlocals).  
  
Vytvoří čítač pro vybrané místní proměnné metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekt představující adresa pro ladění, který vybere kontextu nebo oboru, ze kterého se má získat oknech místní hodnoty.  
  
 `ppLocals`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam lokální; v opačném případě vrátí hodnotu null, pokud neexistují žádné místní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné místní hodnoty. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jsou uvedené pouze proměnné definované v rámci bloku, který obsahuje adresu daného ladění. V případě potřeby jsou všechny lokální proměnné, včetně všech místních hodnot vygenerovaný kompilátorem, zavolejte [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md) metody.  
  
 Metoda může obsahovat více bloků nebo kontextu oboru. Například následující contrived metoda obsahuje tři obory, dvě vnitřní bloky a samotné tělo metody.  
  
```csharp  
public void func(int index)  
{  
    // Method body scope  
    int a = 0;  
    if (index == 1)  
    {  
        // Inner scope 1  
        int temp1 = a;  
    }  
    else  
    {  
        // Inner scope 2  
        int temp2 = a;  
    }  
}  
```  
  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objekt představuje `func` metoda sama. Volání `EnumLocals` metodou [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) nastavena na `Inner Scope 1` vrátí adresu obsahující Výčet `temp1` proměnných, například.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)

