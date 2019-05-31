---
title: 'Postupy: Nastavování atributů CLR v elementu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f9af25934a40c01c6b4cfd48dcd7419bddf322d3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65698019"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vlastní atributy jsou speciální atributy, které lze přidat do domény prvky, tvary, konektory a diagramy. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.  
  
### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut  
  
1. V **Průzkumník DSL**, vyberte požadovaný prvek, ke kterému chcete přidat vlastní atribut.  
  
2. V **vlastnosti** okna, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet ( **...** ) ikonu.  
  
     **Upravit atributy** zobrazí se dialogové okno.  
  
3. V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.  
  
4. Řádek pod názvem atributu zobrazuje závorky. Na tomto řádku zadejte typ parametru atributu (například `string`), a potom stiskněte klávesu ENTER.  
  
5. V **vlastnost Name** sloupce, zadejte vhodný název, například `MyString`.  
  
6. Klikněte na **OK**.  
  
     **Vlastní atributy** vlastnost se nyní zobrazí atribut v následujícím formátu:  
  
     `[` *AttributeName* `(` *ParameterName* `=` *typu* `)]`  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
