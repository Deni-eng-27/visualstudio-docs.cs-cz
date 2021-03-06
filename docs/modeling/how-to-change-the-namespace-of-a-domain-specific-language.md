---
title: 'Postupy: Změna oboru názvů jazyka specifického pro doménu'
description: Poskytuje informace o tom, jak změnit obor názvů jazyka specifického pro doménu.
ms.date: 10/31/2018
ms.topic: how-to
titleSuffix: ''
helpviewer_keywords:
- Domain-Specific Language, namespace
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: SEO-VS-2020
ms.workload:
- multiple
ms.openlocfilehash: a7b0de26fdc1a7982347a12c283a6aa73e9aad12
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2020
ms.locfileid: "90809437"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Postupy: Změna oboru názvů jazyka specifického pro doménu

Můžete změnit obor názvů jazyka specifického pro doménu. Proveďte změnu v **Průzkumníkovi DSL**ve vlastnostech projektu balíčku DSL a v informacích o sestavení.

## <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Změna oboru názvů jazyka specifického pro doménu

1. V **Průzkumníku DSL**vyberte uzel **DSL** .

2. V okně **vlastnosti** změňte vlastnost **Namespace** .

3. Uložte řešení a Transformujte šablony.

4. V nabídce **projekt** vyberte **vlastnosti DSL**.

   Zobrazí se vlastnosti projektu.

5. Vyberte kartu **aplikace** .

6. Změňte **výchozí vlastnost Namespace** na název nového oboru názvů.

7. Pokud chcete také změnit název sestavení, změňte **vlastnost název sestavení.**

8. Pokud jste změnili název sestavení, otevřete DslPackage\Package.tt a aktualizujte tento řádek:

   `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Pokud jste napsali vlastní kód, nezapomeňte změnit obor názvů a odkazy na třídy v souborech kódu.

10. Resetovat experimentální instanci sady Visual Studio.

    1. Odstraňte **\ \\ \Users**_{Name}_**\AppData\Local\Microsoft\VisualStudio \\ \* exp**.

    2. V nabídce **Start** systému Windows vyberte **všechny programy**  >  **Microsoft Visual Studio 2010 SDK**  >  **nástroje**  >  **obnovit experimentální instanci**.

11. V nabídce **sestavení** klikněte na příkaz **znovu sestavit řešení**.

## <a name="see-also"></a>Viz také

[Glosář nástrojů jazyka specifického pro doménu](/previous-versions/bb126564(v=vs.100))