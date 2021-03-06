---
title: Zavést místní proměnnou
description: Vygeneruje místní proměnnou, která nahradí existující výraz. Vyberte výraz, klikněte na něj pravým tlačítkem a vyberte nabídku rychlé akce a refaktoringy, vyberte zavést místní pro (všechny výskyty) výrazu.
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 0fbd5ed752b28cc3f8c0dd734ed2b3ce09e80b78
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75568812"
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Zavedení místní proměnné v aplikaci Visual Studio

Tato generace kódu platí pro:

- C#

- Visual Basic

**Co:** Umožňuje ihned vygenerovat místní proměnnou, která nahradí existující výraz.

**Když:** Máte kód, který můžete později snadno znovu použít, pokud byl v místní proměnné.

**Proč:** Kód můžete zkopírovat a vložit několikrát, abyste ho mohli použít v různých umístěních, ale bylo by lepší provést operaci jednou, uložit výsledek do místní proměnné a použít místní proměnnou v rámci.

## <a name="how-to"></a>Postupy

1. Zvýrazněte výraz, který chcete přiřadit nové místní proměnné.

   - C#:

       ![Zvýrazněný kód C #](media/local-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód VB](media/local-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stiskněte klávesu **CTRL** + **.** pro aktivaci nabídky **rychlé akce a refaktoringy** .
   - **Myš**
      - Klikněte pravým tlačítkem a vyberte nabídku **rychlé akce a refaktoring** .
      - Klikněte na ![screwdriver](media/screwdriver.png) ikona, která se zobrazí na levém okraji, pokud je textový kurzor již na řádku se zvýrazněným výrazem.

   ![Zavést místní náhled](media/local-preview-cs.png)

3. Z rozevírací nabídky vyberte **zavést místní pro (všechny výskyty) výrazu** .

   > [!TIP]
   > Pomocí odkazu **Náhled změn** v dolní části okna Preview [zobrazíte všechny změny](../../ide/preview-changes.md) , které budou provedeny před provedením výběru.

   Lokální proměnná je vytvořena s typem odvozeným z jeho využití. Zadejte nový název místní proměnné.

   - C#:

       ![Implementovat výsledek rozhraní C #](media/local-result-cs.png)

   - Visual Basic:

       ![Implementovat výsledek rozhraní VB](media/local-result-vb.png)

   > [!NOTE]
   > Můžete použít **... všechny výskyty...** možnost nabídky, která nahradí všechny výskyty vybraného výrazu, nikoli jenom ten, který jste výslovně zvýraznili.

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Zobrazit náhled změn](../../ide/preview-changes.md)
