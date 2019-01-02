---
title: IDebugMethodField::EnumLocals | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumLocals
helpviewer_keywords:
- IDebugMethodField::EnumLocals method
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 29e2b79066e34e30f9a07da21ed33c720d135105
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53951797"
---
# <a name="idebugmethodfieldenumlocals"></a>IDebugMethodField::EnumLocals
Vytvoří čítač pro vybrané místní proměnné metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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