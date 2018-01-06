---
title: IDebugDocumentTextEvents2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentTextEvents2
helpviewer_keywords: IDebugDocumentTextEvents2 interface
ms.assetid: a10cbb6b-11a8-4056-b42a-2ecebf0e690d
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bb9e284435cdf8a5905e068b0044cd118a1621c9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumenttextevents2"></a>IDebugDocumentTextEvents2
Toto rozhraní se používá k oznamování změny ve zdrojovém dokumentu, které doplní ladění modul aplikace Visual Studio.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentTextEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní pro podporu změn ke zdrojovému kódu. Toto rozhraní je implementováno obvykle na stejný objekt, který implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]získá toto rozhraní prostřednictvím volání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> metoda. <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> Rozhraní se získávají z volání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A> metoda. <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> Rozhraní se získá voláním [QueryInterface](/cpp/atl/queryinterface) metodu [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugDocumentTextEvents2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[onDestroy](../../../extensibility/debugger/reference/idebugdocumenttextevents2-ondestroy.md)|Označuje, že byl zničen celý dokument.|  
|[onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)|Upozorní balíček ladění, že text byl vložen do dokumentu.|  
|[onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)|Upozorní balíček ladění, text byl odebrán z dokumentu.|  
|[onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)|Upozorní balíček ladění, že text nahrazen v dokumentu.|  
|[onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)|Upozorní balíček ladění, že byly aktualizovány atributy textu v dokumentu.|  
|[onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)|Upozorní příjemce události, že byly aktualizovány atributy dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Pouze ladění strojů, které zadat své vlastní dokumenty by využívat výhod `IDebugDocumentTextEvent2` rozhraní. Příkladem může být skriptovací stroj ladění. Probíhá interpretace skripty, nové zdrojový kód lze vygenerovat, není k dispozici v žádném souboru disk a je zřejmé, pouze je DE.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)