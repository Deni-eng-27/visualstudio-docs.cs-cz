---
title: IDebugDocumentTextEvents2 | Dokumenty společnosti Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentTextEvents2
helpviewer_keywords:
- IDebugDocumentTextEvents2 interface
ms.assetid: a10cbb6b-11a8-4056-b42a-2ecebf0e690d
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44a1736890ac78e7aaf20b4a639b1794fc63b5ac
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2020
ms.locfileid: "80731363"
---
# <a name="idebugdocumenttextevents2"></a>IDebugDocumentTextEvents2
Toto rozhraní slouží k upozornění sady Visual Studio na změny zdrojového dokumentu, které jsou poskytovány ladicí modul.

## <a name="syntax"></a>Syntaxe

```
IDebugDocumentTextEvents2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní pro podporu provádění změn zdrojového kódu. Toto rozhraní je obvykle implementováno na stejném objektu, který implementuje rozhraní [IDebugDocument2.](../../../extensibility/debugger/reference/idebugdocument2.md)

## <a name="notes-for-callers"></a>Poznámky pro volající
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]získá toto rozhraní prostřednictvím <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> volání metody. Rozhraní <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> je získáno z <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A> volání metody. Rozhraní <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> je získáno voláním metody [QueryInterface](/cpp/atl/queryinterface) v rozhraní [IDebugDocument2.](../../../extensibility/debugger/reference/idebugdocument2.md)

## <a name="methods-in-vtable-order"></a>Metody v pořadí Vtable
 V následující tabulce jsou `IDebugDocumentTextEvents2`uvedeny metody .

|Metoda|Popis|
|------------|-----------------|
|[onDestroy](../../../extensibility/debugger/reference/idebugdocumenttextevents2-ondestroy.md)|Označuje, že celý dokument byl zničen.|
|[onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)|Upozorní ladicí balíček, že text byl vložen do dokumentu.|
|[onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)|Upozorní ladicí balíček, že text byl odebrán z dokumentu.|
|[onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)|Upozorní ladicí balíček, že text byl v dokumentu nahrazen.|
|[onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)|Upozorní ladicí balíček, že textové atributy byly aktualizovány v dokumentu.|
|[onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)|Upozorní příjemce události, že atributy dokumentu byly aktualizovány.|

## <a name="remarks"></a>Poznámky
 Pouze ladění motory, které poskytují své vlastní `IDebugDocumentTextEvent2` dokumenty by využít rozhraní. Příkladem tohoto by skriptování ladicí stroj. V procesu interpretace skriptů může být generován nový zdrojový kód, který není přítomen v žádném souboru disku a je znám pouze DE.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
