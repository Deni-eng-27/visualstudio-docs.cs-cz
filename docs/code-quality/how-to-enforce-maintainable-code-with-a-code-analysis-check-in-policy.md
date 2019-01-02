---
title: 'Postupy: Vynucování Udržovatelného kódu pomocí zásady vracení se změnami kód analýzy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7d31e52ab2f158b73a0076414b6d18e0b7421b04
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53825710"
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Postupy: Vynucování udržovatelného kódu pomocí zásady vracení se změnami kód analýzy

Vývojářům nástroj metriky kódu slouží k měření složitosti a udržovatelnosti kódu, ale nejde vyvolat metriky kódu jako součást zásady vrácení se změnami. Můžete ale povolit pravidel analýzy kódu, které ověřují kódu dodržování standardů metrik kódu a vynucení pravidel prostřednictvím zásad vrácení se změnami. Další informace o metrikách kód, naleznete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

Můžete povolit hloubku dědičnosti, párování tříd, Index udržovatelnosti a složitosti pravidla k vynucení udržovatelného kódu pomocí zásad vracení se změnami analýzy kódu. Všechny čtyři tato pravidla se nacházejí v kategorii "Pravidla udržovatelnosti" v editoru zásad analýzy kódu.

Správci verzí pro Team Foundation můžete přidat pravidla udržovatelnosti analýzy kódu pro splnění požadavků zásad vrácení se změnami. Toto vrácení se změnami, že vývojáři pro spuštění na základě těchto pravidel změn před zahájením vrácení se změnami analýzy kódu vyžadují zásady.

## <a name="to-open-the-code-analysis-policy-editor"></a>Otevřete editor zásad analýzy kódu

1. V **Team Exploreru**, klikněte pravým tlačítkem na projekt, klikněte na tlačítko **nastavení projektu**a potom klikněte na tlačítko **správy zdrojových kódů**.

     **Správy zdrojových kódů** zobrazí se dialogové okno.

2. Na **zásad vrácení se změnami** kartu a klikněte na tlačítko **přidat**.

     **Přidat zásady vrácení se změnami** zobrazí se dialogové okno.

3. V **zásad vrácení se změnami** seznamu, vyberte **analýzy kódu** zaškrtněte políčko a potom klikněte na tlačítko **OK**.

     **Editor zásad analýzy kódu** zobrazí se dialogové okno.

## <a name="to-enable-code-analysis-maintainability-rules"></a>Povolení pravidla udržovatelnosti analýzy kódu

1. V **Editor zásad analýzy kódu** dialogovém okně **nastavení pravidla**, rozbalte **pravidla udržovatelnosti** uzlu.

2. Zaškrtněte políčka pro následující pravidla:

   - Hloubka dědičnosti: **CA1501 AvoidExcessiveInheritance** – prahová hodnota: Upozornění na více než 5 úrovní do hloubky

   - Složitost: **CA1502 AvoidExcessiveComplexity** – prahová hodnota: Upozornění na více než 25

   - Index udržovatelnosti: **CA1505 AvoidUnmaintainableCode** – prahová hodnota: Upozornění na méně než 20

   - Párování tříd: **CA1506 AvoidExcessiveClassCoupling** – prahová hodnota: Upozornění na více než 80 pro třídu a více než 30 pro metodu

     Kromě toho pokud chcete porušení pravidla, aby se zabránilo úspěšné sestavení, vyberte **zpracovávat upozornění jako chyba** zaškrtněte políčko vedle popis pravidla.

3. Klikněte na **OK**. Nové zásady vrácení se změnami nyní platí pro budoucí vrácení se změnami.

## <a name="see-also"></a>Viz také:

- [Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
- [Vytváření a používání zásad vrácení se změnami analýzy kódu](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)