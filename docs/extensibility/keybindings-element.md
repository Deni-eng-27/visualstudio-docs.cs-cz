---
title: Keybindings – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- KeyBindings
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBindings element (VSCT XML schema)
ms.assetid: 26a15d5c-ddea-4977-af7f-d795ff09c7ad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4caecb1af8e620c671d5c2cc63e032ad5e1df26d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920640"
---
# <a name="keybindings-element"></a>Keybindings – element
Keybindings – element seskupí prvky klávesové zkratky a další seskupení klávesové zkratky.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<KeyBindings>  
  <KeyBinding>... </KeyBinding>  
  <KeyBinding>... </KeyBinding>  
</KeyBindings>  
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
|[Keybinding – element](../extensibility/keybinding-element.md)|Určuje klávesové zkratky pro příkazy.|  
|[Klávesové zkratky](../extensibility/keybindings-element.md)|Seskupí elementy klávesové zkratky a další seskupení klávesové zkratky.|  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy.|  
  
## <a name="example"></a>Příklad  
  
```xml  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Keybinding – element](../extensibility/keybinding-element.md)   
 [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)