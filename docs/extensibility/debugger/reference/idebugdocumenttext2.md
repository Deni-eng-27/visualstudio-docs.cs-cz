---
title: IDebugDocumentText2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentText2
helpviewer_keywords: IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebcb90f570ad29f38eabe8712928b484fd6961c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
Toto rozhraní představuje textový dokument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentText2 : IDebugDocument2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje modul ladění (DE) Pokud je zdrojový kód, který je potřeba zadat v textové podobě. Vzhledem k tomu, že toto je nejčastější případ, pokud Zavedenými implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní, se musí také implementovat `IDebugDocumentText2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití `QueryInterface` metodu k získání tohoto rozhraní z `IDebugDocument2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na `IDebugDocument2` rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getsize –](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|Velikost textu v této pozici v dokumentu načte.|  
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|Načte text z konkrétní pozici v dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Také musí implementovat objekt, který implementuje toto rozhraní <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní, které zdroje <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní pro [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) objektu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)