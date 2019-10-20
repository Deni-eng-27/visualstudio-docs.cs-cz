---
title: 'Postupy: Zobrazení existujících typů (návrhář tříd)'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.CannotShowBaseType
helpviewer_keywords:
- types [Visual Studio], visualizing
- types [Visual Studio], class diagrams
- class diagrams, types
ms.assetid: de110a4e-5b51-4a40-9dee-615df4d8f999
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 386b62e278b1fbe8230af16b54f8b7bb95857c48
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72631535"
---
# <a name="how-to-view-existing-types-in-class-designer"></a>Postupy: zobrazení existujících typů v Návrhář tříd

Chcete-li zobrazit existující typ a jeho členy, přidejte její tvar do diagramu tříd.

Můžete vidět místní a odkazované typy. V aktuálně otevřeném projektu existuje místní typ a je pro čtení i zápis. Odkazovaný typ existuje v jiném projektu nebo v odkazovaném sestavení a je jen pro čtení.

Chcete-li navrhnout nové typy v diagramech tříd, přečtěte si téma [Postupy: vytváření typů pomocí Návrhář tříd](how-to-create-types.md).

## <a name="to-see-types-in-a-project-on-a-class-diagram"></a>Zobrazení typů v projektu v diagramu tříd

1. Z projektu v **Průzkumník řešení**otevřete existující soubor diagramu tříd (. CD). Nebo pokud neexistuje žádný diagram tříd, přidejte do projektu nový diagram tříd. Viz [Postupy: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).

2. Z projektu v **Průzkumník řešení**přetáhněte soubor zdrojového kódu do diagramu tříd.

    > [!NOTE]
    > Pokud má vaše řešení projekt, který sdílí kód napříč více aplikacemi, můžete přetáhnout soubory nebo kód do diagramu tříd pouze z těchto zdrojů:
    >
    > - Projekt aplikace, který obsahuje diagram
    > - Sdílený projekt, který byl importován projektem aplikace
    > - Odkazovaný projekt
    > - Sestavení

    Tvary, které představují typy definované v souboru zdrojového kódu, se zobrazí v diagramu na pozici, kam jste soubor přetáhli.

Můžete také zobrazit typy v projektu přetažením jednoho nebo více typů z uzlu projektu v **zobrazení tříd** do diagramu tříd.

> [!TIP]
> Pokud **zobrazení tříd** není otevřený, otevřete **zobrazení tříd** v nabídce **zobrazení** .

Chcete-li zobrazit typy ve výchozích umístěních v diagramu, vyberte jeden nebo více typů v **zobrazení tříd**, klikněte pravým tlačítkem myši na vybrané typy a zvolte možnost **Zobrazit diagram tříd**.

> [!NOTE]
> Pokud v projektu existuje zavřený diagram tříd obsahující daný typ, diagram tříd se otevře a zobrazí tvar typu. Nicméně pokud v projektu neexistuje žádný diagram tříd obsahující daný typ, **Návrhář tříd** vytvoří nový diagram tříd v projektu a otevře jej pro zobrazení typu.

Při prvním zobrazení typu v diagramu se jeho tvar ve výchozím nastavení zobrazí sbalený. Tvar můžete rozbalit a zobrazit jeho obsah.

### <a name="to-display-the-contents-of-a-project-in-a-class-diagram"></a>Zobrazení obsahu projektu v diagramu tříd

V **Průzkumník řešení** nebo **zobrazení tříd**klikněte pravým tlačítkem myši na projekt a zvolte možnost **Zobrazit**a pak zvolte možnost **Zobrazit diagram tříd**. Vytvoří se automaticky vyplněný diagram tříd.

## <a name="see-also"></a>Viz také:

- [Postupy: zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)
- [Postupy: přizpůsobení diagramů tříd](how-to-customize-class-diagrams.md)
- [Zobrazování typů a vztahů](designing-and-viewing-classes-and-types.md)