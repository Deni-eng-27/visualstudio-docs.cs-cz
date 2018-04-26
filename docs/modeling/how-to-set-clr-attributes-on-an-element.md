---
title: 'Postupy: Nastavování atributů CLR v elementu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ceca2556e269d554d40e025e5edcb91753149622
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
Vlastní atributy jsou speciální atributy, které mohou být přidány do domény prvky, tvarů, konektory a diagramů. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.

### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut

1.  V **DSL Explorer**, vyberte požadovaný prvek, ke které chcete přidat vlastní atribut.

2.  V **vlastnosti** okno, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet (**...** ) ikona.

     **Upravit atributy** otevře se dialogové okno.

3.  V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.

4.  Řádek v části název atributu zobrazí závorek. Na tomto řádku zadejte typ parametru pro atribut (například `string`), a stiskněte klávesu ENTER.

5.  V **vlastnost Name** sloupce, zadejte odpovídající název, například `MyString`.

6.  Click **OK**.

     **Vlastní atributy** vlastnost teď zobrazuje atribut v následujícím formátu:

     `[` *AttributeName* `(` *ParameterName* `=` *typu* `)]`

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)