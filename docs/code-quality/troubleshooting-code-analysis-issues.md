---
title: Řešení potíží s Analýzou kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 34fce91db15d484b140aee291f9abd915d9399d2
ms.sourcegitcommit: 159ed9d4f56cdc1dff2fd19d9dffafe77e46cd4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/21/2018
ms.locfileid: "53738790"
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
Toto téma obsahuje informace o odstraňování potíží pro následující problémy s analýzou kódu sady Visual Studio.

-   [Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio](#ChildRuleSetChangesInPreviousVersions)

##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio
 Když vytvoříte pravidlo nastavit [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] , která obsahuje podřízenou sadu pravidel, nejde použít ke změně podřízené sady pravidel v nastavují spuštění analýzu kódu na počítačích, které používají starší verzi sady Visual Studio. Pokud chcete tento problém vyřešit, musíte Vynutit přepsání sady pravidel nadřazený, který je sada pravidel, která obsahuje podřízené sady pravidel.

1. Otevřít nadřazený pravidlo nastavené [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

2. Proveďte změnu, jako je například přidávání nebo odebírání pravidlo a potom uložte sady pravidel.

3. Znovu otevřít sadu pravidel, zrušení změny a potom uložte pravidlo znovu nastavit.

## <a name="see-also"></a>Viz také
 [Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md) [analýza kvality spravovaného kódu](../code-quality/code-analysis-for-managed-code-overview.md) [použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)