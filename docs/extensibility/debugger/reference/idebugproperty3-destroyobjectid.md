---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3e6679c35452c63009046afb275922188d4fede6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54916352"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Zničí jedinečné ID přidružené k této vlastnosti označující, že volající už zdroje k identifikaci této vlastnosti jednoznačně z dalších vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ladicí stroj nemusí podporovat jedinečné ID pro vlastnost (protože je již sleduje je jednoznačně interně), pak můžete jednoduše vrátit `E_NOTIMPL` pro tuto metodu.  
  
 Jedinečné ID se vytváří pomocí volání [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) v případě, že volající vyžaduje, abyste měli jistotu, že tato vlastnost je jednoznačně identifikují mimo jiné vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)