---
title: "Postupy: určení sad pravidel spravovaného kódu pro více projektů v určitém řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.solution
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: e0b6a2864340f87702b765f49605ebdb3aaa555c
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2018
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>Postupy: Určení sad pravidel spravovaného kódu pro více projektů v určitém řešení

Ve výchozím nastavení, všechny projekty, které jsou spravované řešení přiřazené analýza kódu Microsoft Minimální doporučená pravidla *sadu pravidel*. Sady pravidel, které jsou přiřazeny k projektům řešení v dialogovém okně Vlastnosti pro řešení, můžete změnit.

> [!NOTE]
> Analýza kódu projektu není ve výchozím nastavení spustí jako krok sestavení. Analýza kódu jako krok sestavení povolit, najdete v části [postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).

1. Otevřete řešení v sadě Visual Studio.

2. Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro řešení**.

3. V případě potřeby rozbalte **společných vlastností**a potom klikněte na **nastavení analýzy kódu**.

4. Můžete zadat sadu pravidel pro jednoho nebo několika projektů.

    - Pokud chcete zadat sadu pravidel pro jednotlivé projektu, klikněte na název projektu.

    - Pokud chcete zadat sadu pravidel pro více projektů, podržte klávesu CTRL a klikněte na název projektu.

    - Chcete-li zadat všechny projekty v řešení, podržte stisknutou klávesu SHIFT a klikněte v seznamu projektu.

5. Klikněte **pravidlo nastavené** pole projektu a pak klikněte na název pravidla nastavit, že chcete použít.