---
title: Řešení potíží s analýzou kódu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6fd2735b7e601afb5a80dd027a8ae107cab58e4a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72672425"
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto téma obsahuje informace o řešení potíží pro následující problémy analýzy kódu sady Visual Studio.

- [Změny v sadě pravidel sady Visual Studio 2010 se neprojeví v předchozích verzích sady Visual Studio.](#ChildRuleSetChangesInPreviousVersions)

## <a name="changes-in-a-visual-studio-2010-rule-set-are-not-reflected-in-previous-visual-studio-versions"></a><a name="ChildRuleSetChangesInPreviousVersions"></a> Změny v sadě pravidel sady Visual Studio 2010 se neprojeví v předchozích verzích sady Visual Studio.
 Když vytvoříte sadu pravidel v [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] , která obsahuje podřízenou sadu pravidel, změna podřízené sady pravidel se nemusí použít při spuštění analýzy kódu na počítačích, které používají starší verzi sady Visual Studio. Chcete-li tento problém vyřešit, je nutné vynutit přepsání sady nadřazených pravidel, což je sada pravidel, která obsahuje sadu podřízených pravidel.

1. Otevřete nadřazenou sadu pravidel v [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .

2. Proveďte změnu, například přidání nebo odebrání pravidla, a potom sadu pravidel uložte.

3. Znovu otevřete sadu pravidel, převratte změnu a znovu uložte sadu pravidel.

## <a name="see-also"></a>Viz také
 [Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md) [Analýza spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md) [pomocí sad pravidel pro seskupení pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
