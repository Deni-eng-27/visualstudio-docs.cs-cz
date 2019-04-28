---
title: Stránka Události sestavení, návrhář projektu (C#)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 25ea62284698de9d57cbcbefa73b950af8c42a6f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62790898"
---
# <a name="build-events-page-project-designer-c"></a>Stránka Události sestavení, návrhář projektu (C#)
Použití **události sestavení** stránku **Návrháře projektu** k určení pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých jsou spuštěny žádné události po sestavení. Další informace najdete v tématu [jak: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)a [jak: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Konfigurace** tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku, naleznete v tématu [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Platforma** tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku, naleznete v tématu [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

 **Příkazový řádek události před sestavením** Určuje všechny příkazy se mají provést před začátkem sestavení. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit před sestavením** zobrazíte [pre-build Event/po sestavení příkazového řádku dialogové okno události](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Události před sestavením nebudou spuštěny, pokud je aktuální projekt a není aktivováno žádné sestavení.

 **Příkazový řádek události po sestavení** Určuje všechny příkazy k provedení po skončení sestavování. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit POST-Build** zobrazíte **pre-build Event/po sestavení příkazového řádku dialogové okno události**.

> [!NOTE]
> Přidat `call` než vše post-build příkazy, které spouštějí soubory .bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.

 **Spustit událost po sestavení** určuje následující podmínky pro událost po sestavení ke spuštění, jak je znázorněno v následující tabulce.

|Možnost|Výsledek|
|------------|------------|
|**Vždy**|Událost po sestavení se spustí bez ohledu na to, zda byl sestaven úspěšně.|
|**Při úspěšném sestavení**|Událost po sestavení spustí-li sestavení úspěšné. Díky tomu se událost se spustí i pro projekt, který je aktuální, tak dlouho, dokud sestavení úspěšné.|
|**Když sestavení aktualizuje výstup projektu**|Událost po sestavení poběží pouze po kompilátoru výstupního souboru (.exe nebo .dll) se liší od předchozí výstupní soubor kompilátoru. Událost po sestavení se díky tomu se nespustil, když je aktuální projekt.|

## <a name="see-also"></a>Viz také

- [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Postupy: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)
- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)