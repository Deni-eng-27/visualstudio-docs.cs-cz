---
title: Commandplacements – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CommandPlacements
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 78a5724a-3b9f-4c78-9c0d-8faa3924f81c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 923ba2a517ae934fb83c0cb36a29dbe518a2a2a3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991057"
---
# <a name="commandplacements-element"></a>Commandplacements – element
Commandplacements – element seskupí commandplacement – elementy a ostatní commandplacements – seskupení.  
  
 Commandplacements – element je volitelné. Pokud v nějakém sekundárním umístění musí obsahovat žádné příkazy, skupiny nebo nabídky, není potřeba zahrnovat v této části vašeho *.vsct* souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<CommandPlacements>  
  <CommandPlacement>... </CommandPlacement>  
  <CommandPlacement>... </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Commandplacements –|Seskupí commandplacement – elementy a ostatní commandplacements – seskupení.|  
|[Commandplacement – element](../extensibility/commandplacement-element.md)|Umožňuje tlačítka, skupiny a nabídek, které mají být zahrnuty do více než jedné skupině nebo v nabídce.|  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy.|  
  
## <a name="example"></a>Příklad  
  
```xml  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Commandplacement – element](../extensibility/commandplacement-element.md)   
 [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)