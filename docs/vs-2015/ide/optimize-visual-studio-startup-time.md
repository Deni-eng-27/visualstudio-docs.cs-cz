---
title: Optimalizace času spuštění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.topic: conceptual
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing startup time [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0ceed13cc320e2c98d413e6694acb2b473ad72eb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780272"
---
# <a name="optimize-visual-studio-startup-time"></a>Optimalizace spouštění sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V ideálním případě sady Visual Studio by měl vždy spustit co nejrychleji. Však rozšíření sady Visual Studio a otevřete nástroj windows mohou nepříznivě ovlivnit rychlost spuštění vzhledem k tomu, že se načítají automaticky při spuštění. **Spravovat výkon sady Visual Studio** okno umožňuje zobrazit nejen funkce a rozšíření, které ovlivňují spouštění sady Visual Studio, ale také umožňuje určit jejich chování při načítání, takže budete mít větší kontrolu nad jak rychle Spuštění sady Visual Studio.

## <a name="control-startup-behavior"></a>Řízení chování při spuštění

Aby se zabránilo rozšíření čas spuštění, Visual Studio 2017 nevyužívá během spouštění, načítání rozšíření metodiky zatížení na vyžádání. To znamená, že rozšíření neotevírat ihned poté, co Visual Studio spustí, ale místo toho otevřít asynchronně účtujeme podle potřeby po spuštění. Protože okna nástrojů ponechány otevřené v předchozí relaci sady Visual Studio může zhoršit dobu spuštění, Visual Studio otevře okna nástrojů inteligentnější způsobem, aby se zabránilo dopadu na dobu spuštění.

Pokud sada Visual Studio zjistí pomalé spouštění, zobrazí se místní zpráva, upozorní vás do okna rozšíření nebo nástroj, který je příčinou zpomalení. Zprávy také obsahuje odkaz **spravovat výkon sady Visual Studio** dialogové okno, které obsahuje nástroje a rozšíření windows, které mají vliv na výkon při spuštění. Toto dialogové okno umožňuje změnit nastavení okna nástroje a rozšíření pro zvýšení výkonu při spuštění.

![Spravovat výkon sady Visual Studio – automaticky otevírané okno](../ide/media/vside-perfdialog-popup.PNG "spravovat výkon sady Visual Studio – automaticky otevíraného okna")

**Spravovat výkon sady Visual Studio** dialogové okno obsahuje dvě kategorie: **Rozšíření** a **nástroj Windows**.

### <a name="control-extensions"></a>Rozšíření pro ovládací prvky
Pokud rozšíření je zpomalení při spuštění sady Visual Studio, rozšíření se zobrazí v **dialogového okna spravovat výkon sady Visual Studio** pole při výběru jednoho z typů rozšíření. Pokud dopad na dobu spuštění (které je uvedené v části **dopad** oddíl) je nepřijatelně vysoké, můžete nastavit výběrem vždy zakázat rozšíření při spuštění **zakázat** tlačítko. Rozšíření pro budoucí relace můžete znovu povolit pomocí Správce rozšíření nebo dialogovém okně Spravovat výkon sady Visual Studio.

![Spravovat výkon sady Visual Studio – rozšíření](../ide/media/vside-perfdialog-extensions.PNG "spravovat výkon sady Visual Studio – rozšíření")

Kromě spuštění rozšíření můžete také zakázat rozšíření, který se načítá při načítání řešení, nebo když uživatel zadá. Zvolte pouze scénář zobrazíte seznam přidružených rozšíření.

### <a name="control-tool-windows"></a>Řízení oken nástrojů
Pokud panel nástrojů je zpomalení při spuštění sady Visual Studio, můžete také ponechat jeho výchozí chování (díky tomu získáte žádné výhody v rychlost při spouštění) nebo jeho chování můžete přepsat volbou jedné z dvou chování:

- **Nezobrazovat okno při spuštění:** Pokud zvolíte tuto možnost, v okně zadaného nástroje vždy se zavřou při otevření sady Visual Studio, i v případě, že ponechány otevřené v předchozí relaci. Panel nástrojů můžete otevřít z nabídky.
- **Automaticky skrýt okno při spuštění:** Pokud v předchozí relace byla otevřená okna nástroje, pokud vyberete tuto možnost bude sbalit panel nástrojů skupinu při spuštění inicializace panel nástrojů, aby. To je dobrou volbou, pokud používáte panelu nástrojů často, protože okno nástroje je stále k dispozici, ale má vliv na už nebude mít negativní čas spuštění sady Visual Studio.

![Spravovat výkon sady Visual Studio – okna nástrojů](../ide/media/vside-perfdialog-toolwindows.PNG "spravovat výkon sady Visual Studio – oken nástrojů")

Pokud později změníte své rozhodnutí, můžete některé z těchto možností v vrátit **spravovat výkon sady Visual Studio** dialogové okno. Chcete-li otevřít **spravovat výkon sady Visual Studio** dialogové okno, v panelu nabídky zvolte **pomáhají**, **spravovat výkon sady Visual Studio**.
