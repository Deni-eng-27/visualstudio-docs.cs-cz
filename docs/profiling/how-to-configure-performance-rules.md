---
title: 'Postupy: Konfigurace pravidel výkonu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0713296cd9b9b35caf12608f177e43ba6447106c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56634731"
---
# <a name="how-to-configure-performance-rules"></a>Postupy: Konfigurace pravidel výkonu
Upozornění výkonu th Visual Studio nástrojů pro profilaci sady signalizují potíže v profilované aplikaci, která může zpomalit spuštění programu. Upozornění lze také určit, že může být nutné změnit metody kolekce shromažďovat užitečnější data. Upozornění výkonu jsou automaticky generovány v relaci profilace a zobrazí v **seznam chyb** okno při otevření souboru dat profilování v [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. Některé upozornění nemusí platit pro scénáře, že máte zájem, a upozorněním mohla být vyvolána nesprávně vykázán. Můžete nakonfigurovat upozornění výkonu zobrazení nebo skrytí konkrétního upozornění.

### <a name="to-configure-profiler-performance-warnings"></a>Konfigurace upozornění profileru výkonu

1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

2.  Rozbalte **nástroje pro měření výkonu**a potom klikněte na tlačítko **pravidla**.

3.  Pokud chcete povolit nebo zakázat upozornění, zaškrtněte nebo zrušte zaškrtnutí políčka u upozornění **ID** a název.

4.  K určení úrovně warring pravidla, klikněte na tlačítko **akce** buňka vedle pravidlo a pak klikněte na úroveň pro upozornění.

    -   **Zakázané** – zakáže pravidlo (to je stejný jako zrušením zaškrtnutí políčka vedle ID pravidla).

    -   **Upozornění** -pravidlo zobrazí jako varování.

    -   **Chyba** – zastaví spuštění profilace a zobrazí pravidlo jako chyba.

    -   **Informace o** -zobrazí pravidlo jako pouze informace.