---
title: Idiastackwalker – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67c19b37fbe6d5867e44a81233c44aceb5138b68
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227222"
---
# <a name="idiastackwalker"></a>IDiaStackWalker
Poskytuje metody, jak provést zásobníku provede pomocí informací v souboru .pdb.

## <a name="syntax"></a>Syntaxe

```
IDiaStackWalker: IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaStackWalker`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|Načte čítač rámce zásobníku pro x86 platformy.|
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|Načte čítač rámce zásobníku pro typ konkrétní platformy.|

## <a name="remarks"></a>Poznámky
Toto rozhraní se používá k získání seznamu sad rámců zásobníku u načteného modulu. Každá z metod je předán [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) objektu (implementované klientské aplikace), který poskytuje informace potřebné k vytvoření seznamu rámce zásobníku.

## <a name="notes-for-callers"></a>Poznámky pro volající
Toto rozhraní je získán voláním `CoCreateInstance` metoda s identifikátorem třídy `CLSID_DiaStackWalker` a interface ID `IID_IDiaStackWalker`. Příklad ukazuje, jak získat toto rozhraní.

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak získat `IDiaStackWalker` rozhraní.

```C++

IDiaStackWalker* pStackWalker;
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,
                              NULL,
                              CLSCTX_INPROC_SERVER,
                              IID_IDiaStackWalker,
                              (void**) &pStackWalker);
if (FAILED(hr))
{
    // Report error and exit
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: Dia2.h

Knihovna: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
[Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)  
[IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
