---
title: IDebugProperty3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3
helpviewer_keywords:
- IDebugProperty3 interface
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8581e8163ab95eac7d49c5deca70c339804aac64
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348705"
---
# <a name="idebugproperty3"></a>IDebugProperty3
Toto rozhraní poskytuje podporu pro:

- Načítání libovolně dlouhý řetězec přidružený k vlastnosti.

- Jedinečné ID přiřazení s vlastností.

- Načítání seznamu vlastních prohlížečů pro vlastnost.

- Nastavení hodnoty vlastnosti umožňuje nahlásit případné chyby

## <a name="syntax"></a>Syntaxe

```
IDebugProperty3 : IDebugProperty2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní na stejný objekt, který implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) k poskytování podpory pro dlouhé řetězce, vlastnosti ID a vlastních prohlížečů.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProperty2` rozhraní k získání tohoto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z `IDebugProperty2`, `IDebugProperty3` rozhraní poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|Vrátí délku řetězce spojeného s vlastností.|
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|Vrátí řetězec do uživatelem zadané vyrovnávací paměti.|
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|Vytvoří jedinečné ID pro tuto vlastnost.|
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|Zničí jedinečné ID pro tuto vlastnost.|
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|Vrátí počet vlastních prohlížečů, které se dají zobrazit tuto vlastnost.|
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|Vrátí seznam vlastních prohlížečů, které se dají zobrazit tuto vlastnost.|
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|Nastaví hodnotu této vlastnosti, vrátí chybovou zprávu, pokud se něco pokazilo.|

## <a name="remarks"></a>Poznámky
- [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) je upřednostňovaný způsob pro správce ladění relace (SDM) k nastavení hodnoty vlastnosti.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)