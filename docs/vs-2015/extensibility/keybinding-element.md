---
title: Keybinding – Element | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 808897b632353e47185cdbd5606d6f2eed1361b0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49231813"
---
# <a name="keybinding-element"></a>KeyBinding – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Keybinding – element určuje klávesové zkratky pro příkazy.  
  
 Příkazy může mít jeden a duální klávesové zkratky, které jsou k nim má přiřazené. Příkladem jednoho vazbu klíče je CTRL + S pro **Uložit** příkazu. Duální klávesové zkratky vyžadují dvě po sobě jdoucích kombinace kláves pro spuštění příkazu. Příklad duální vazba klíče je CTRL + K, CTRL + K, chcete-li nastavit záložky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Požadováno.|  
|id|Požadováno.|  
|editor|Požadováno. Identifikátor GUID editoru určuje kontext úprav, pro kterou bude klávesová zkratka aktivní. Hodnota oboru globální vazby je "guidVSStd97".|  
|key1|Požadováno. Platné hodnoty jsou všechny typable alfanumerické znaky a také předchází 0 x a VK_constants šestnáctkové hodnoty dvou číslic.|  
|mod1|Volitelné. Libovolnou kombinaci CTRL, ALT a SHIFT odděleny mezerou.|  
|key2|Volitelné. Platné hodnoty jsou všechny typable alfanumerické znaky a také předchází 0 x a VK_constants šestnáctkové hodnoty dvou číslic.|  
|mod2|Volitelné. Libovolnou kombinaci CTRL, ALT a SHIFT odděleny mezerou.|  
|Emulátor|Volitelné.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené||  
|Poznámka||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[KeyBindings – element](../extensibility/keybindings-element.md)|Seskupí elementy klávesové zkratky a další seskupení klávesové zkratky.|  
  
## <a name="example"></a>Příklad  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Viz také  
 [Keybindings – Element](../extensibility/keybindings-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

