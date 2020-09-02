---
title: IDiaStackWalker | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d6f5f5c3fa70c022175208cee492f3c0e752826e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68144687"
---
# <a name="idiastackwalker"></a>IDiaStackWalker
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Poskytuje metody pro procházení zásobníku pomocí informací v souboru. pdb.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDiaStackWalker: IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable  
 V následující tabulce jsou uvedeny metody `IDiaStackWalker` .  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|Načte enumerátor rámce zásobníku pro platformy x86.|  
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|Načte enumerátor rámce zásobníku pro konkrétní typ platformy.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní slouží k získání seznamu rámců zásobníku pro načtený modul. Každá z metod je předána objektu [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) (implementováno klientskou aplikací), který poskytuje potřebné informace pro vytvoření seznamu rámců zásobníku.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získá voláním `CoCreateInstance` metody s identifikátorem třídy `CLSID_DiaStackWalker` a ID rozhraní `IID_IDiaStackWalker` . Příklad ukazuje, jak se toto rozhraní získává.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaStackWalker` rozhraní.  
  
```cpp#  
  
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
 Záhlaví: Dia2. h  
  
 Knihovna: diaguids. lib  
  
 KNIHOVNA DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
