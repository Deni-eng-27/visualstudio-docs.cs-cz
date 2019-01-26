---
title: IEnumCodePaths2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 20bfd418da802e136fd92948285f9431efae88ad
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54982114"
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
Toto rozhraní představuje seznam cest kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumCodePaths2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam cest kódu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) získat toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumCodePaths2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|Načte zadaný počet cest kódu v sekvenci výčtu.|  
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|Vynechá zadaný počet cest kódu v sekvenci výčtu.|  
|[Reset](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Clone](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|Získá počet cest kódu v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Cesta kódu představuje volání větev bodu nebo funkce v programu. Seznam cest kódu představuje cestu, přes který provádění kódu obsazené.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)