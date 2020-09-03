---
title: Připojení referenčních řetězců k prvkům modelu UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- UML - extending, reference strings
ms.assetid: 15dbed99-efce-42fe-a768-714a5804e7d1
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7726379258ef474b57f1ca4a924413cd93cf80bb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72672794"
---
# <a name="attach-reference-strings-to-uml-model-elements"></a>Připojení referenčních řetězců k prvkům modelu UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete napsat kód pro připojení libovolných řetězců k prvkům modelu. Řetězec může být například identifikátor URI, výsledek výpočtu uložený v mezipaměti nebo ModelBus odkaz na element v jiném modelu. Každý řetězec je obsažen v objektu IReference. K jednotlivým prvkům modelu lze připojit libovolný počet objektů IReference.

 Každý objekt IReference má název. Tento název můžete použít k určení, jak by měla být interpretována hodnota odkazu. Například můžete nastavit název na "URI", aby označoval, že hodnota by měla být interpretována jako identifikátor URI. Existují některé předdefinované hodnoty referenčního názvu používané nástroji pro modelování.

## <a name="attaching-a-reference-to-an-ielement"></a>Připojení odkazu k IElement
 Chcete-li použít následující metody, je nutné přidat odkaz na:

 Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll

 Tuto direktivu byste měli vložit do svého kódu:

 `using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;`

|Volání metody|Popis|
|-----------------|-----------------|
|`element.AddReference (nameString, valueString, duplicatesAllowed)`|Vytvoří `IReference` se zadaným řetězcem název a hodnota a propojí ho s `element` . Vrátí `IReference` .<br /><br /> Vyvolá výjimku, pokud `duplicatesAllowed` je false a již existuje objekt `IReference` se stejným názvem, ke kterému je připojen `element` .|
|`element.GetReferences(name)`|Vrátí všechny `IReference` objekty spojené s daným objektem `element` `name` .|
|`element.DeleteAllReferences(name)`|Odstraní všechny `IReference` objekty propojené s prvkem, který má křestní jméno.|
|`reference.Delete()`|Odstraní toto `IReference` .|
|`ReferenceConstants.WorkItem`|Hodnota, která slouží k pojmenování odkazů na pracovní položky.|

## <a name="see-also"></a>Viz také
 [Definice obslužné rutiny propojení pracovní položky](../modeling/define-a-work-item-link-handler.md) [definovat a instalovat programování rozšíření pro modelování](../modeling/define-and-install-a-modeling-extension.md) [pomocí rozhraní API UML](../modeling/programming-with-the-uml-api.md)
