---
title: Použití Node.js REPL
description: Visual Studio poskytuje podporu pro interakci s modulem runtime Node.js.
ms.date: 12/04/2018
ms.topic: how-to
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 8b2bbbdf478f27f936d4897f2ff773baa4cca1d6
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85285001"
---
# <a name="work-with-the-nodejs-interactive-window"></a>Práce s Node.js interaktivním oknem

Nástroje pro Node.js pro Visual Studio obsahují interaktivní okno pro nainstalovanou Node.js modul runtime. Toto okno umožňuje zadat kód jazyka JavaScript a okamžitě zobrazit výsledky a spustit npm příkazy pro interakci s aktuálním projektem. Interaktivní okno se také označuje jako REPL (**R**ečíst/**E**Valuate/**P**isknout **L**OOP).

## <a name="open-the-interactive-window"></a>Otevřít interaktivní okno

Interaktivní okno můžete otevřít tak, že kliknete pravým tlačítkem myši na uzel Node.js projektu v Průzkumník řešení a vyberete **otevřít Node.js interaktivní okno**.

![Node.js interaktivní okno v místní nabídce projektu](../javascript/media/interactivewindow-open-from-project.png)

Výchozí krátké klávesy pro otevření Node.js interaktivní okno jsou **[CTRL] + K, N**. Nebo můžete okno otevřít z panelu nástrojů výběrem možnosti **Zobrazit**  >  **Windows**  >  **Node.js interaktivní okno**.

## <a name="use-the-repl"></a>Použití REPL

Po otevření můžete zadat příkazy.

![Node.js interaktivní okno](../javascript/media/interactivewindow.png)

Interaktivní okno obsahuje několik integrovaných příkazů, které začínají předponou tečky pro jejich odlišení od libovolné funkce JavaScriptu, kterou deklarujete. Podporovány jsou následující příkazy:

**. CLS,. Clear** Vymaže obsah okna editoru a ponechá historii a kontext spuštění beze změny.

**. help** Pokud není zadána žádná hodnota, zobrazí se vám v zadaném příkazu nebo na všech dostupných příkazech a vazbách kláves.

**. info** Zobrazí informace o aktuálně použitém spustitelném souboru Node.js.

**. npm** Spustí příkaz npm. Pokud řešení obsahuje více než jeden projekt, zadejte cílový projekt pomocí `.npm [projectname] <npm arguments>` .

**. Reset** Obnoví spouštěcí prostředí na počáteční stav a uchová historii.

**. Save** Uloží aktuální relaci REPL do souboru.