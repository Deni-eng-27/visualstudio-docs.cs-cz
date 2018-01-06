---
title: "Následníky (vlastnost XElement dynamické) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 12d50f38d8f8d907ddb663a03db459851f1e14e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="descendants-xelement-dynamic-property"></a>Následníky (vlastnost XElement dynamické)
Získá indexeru. používá se k načtení všechny následné prvky aktuálního elementu odpovídající rozšířené zadaný název.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Descendants[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Indexer typu `IEnumerable<XElement> Item(String expandedName)`. Indexer vezme rozbalený název zadaný následnickým elementům a vrátí odpovídající podřízených elementů v <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` kolekce.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je ekvivalentní <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> metodu <xref:System.Xml.Linq.XContainer> třídy.  
  
 Elementy v kolekci vrácený jsou v pořadí dokumentu XML zdrojů.  
  
 Tato vlastnost využívá odložené provedení.  
  
## <a name="see-also"></a>Viz také  
 [Dynamické vlastnosti XElement – třída](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)