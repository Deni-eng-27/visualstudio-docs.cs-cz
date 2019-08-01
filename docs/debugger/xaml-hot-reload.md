---
title: Zápis a ladění XAML pomocí horkého opětovného načtení XAML
description: Hot Reloades XAML nebo upravit a pokračovat v XAML umožňuje provádět změny kódu XAML při spouštění aplikací.
ms.custom: ''
ms.date: 02/28/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1b2428024c30b8f96babf0cab6a56c60f52fa57
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/01/2019
ms.locfileid: "68711224"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>Zápis a ladění spuštěného kódu XAML pomocí programu XAML Hot reloading v aplikaci Visual Studio

Visual Studio XAML Hot Loading vám pomůže sestavit vaše uživatelské rozhraní aplikace WPF nebo UWP tím, že vám umožní v průběhu vaší aplikace dělat změny v kódu XAML. Tato funkce umožňuje přírůstkově sestavovat a testovat kód XAML s výhodou pro datový kontext běžící aplikace, stav ověřování a další složitost reálného světa, která je po dobu návrhu nenáročná na simulaci.

V těchto scénářích je obzvlášť užitečné použití XAML Hot Reload:

* Opravy problémů uživatelského rozhraní nalezené v kódu XAML po spuštění aplikace v režimu ladění.

* Sestavování nové komponenty uživatelského rozhraní pro aplikaci, která je vyvíjena při vývoji, a přitom využití kontextu modulu runtime vaší aplikace.

|Podporované typy aplikací|Operační systém a nástroje|
|-|-|-|
|Windows Presentation Foundation (WPF) |.NET Framework 4.6 +</br>Windows 7 a novější |
|Univerzální aplikace pro Windows (UWP)|Windows 10 a novější s [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> Automatické opětovné načtení v jazyce Visual Studio XAML je aktuálně podporováno pouze při spuštění aplikace v aplikaci Visual Studio s připojeným ladícím programem (**F5** nebo **Spustit ladění**). Toto prostředí nemůžete povolit pomocí možnosti *připojit k procesu*.

## <a name="known-limitations"></a>Známá omezení

Níže jsou známá omezení pro opětovné načtení kódu XAML. Chcete-li obejít jakékoli omezení, které je třeba spustit, stačí zastavit ladicí program a operaci dokončit.

|Omezené|WPF|UWP|Poznámky|
|-|-|-|-|
|Události zapojení do ovládacích prvků, když je aplikace spuštěná|Nepodporováno|Není podporováno|Zobrazit chybu: *Zajistěte selhání události*|
|Vytváření objektů prostředků ve slovníku prostředků, jako jsou například v rámci stránky nebo okna vaší aplikace nebo souboru *App. XAML*|Nepodporováno|Podporováno|Příklad: přidání ```SolidColorBrush``` do slovníku prostředků pro použití ```StaticResource```jako.</br>Poznámka: Statické prostředky, převaděče stylu a další elementy zapsané do slovníku prostředků lze použít nebo použít při použití kódu XAML Hot reloading. Nepodporují se jenom vytváření prostředků.</br> Změna vlastnosti slovníku ```Source``` prostředků.| 
|Přidání nových ovládacích prvků, tříd, oken nebo jiných souborů do projektu v době, kdy aplikace běží|Nepodporováno|Nepodporováno|Žádné|
|Správa balíčků NuGet (přidávání/odebírání a aktualizace balíčků)|Nepodporováno|Nepodporováno|Žádný|
|Změna datové vazby, která používá rozšíření značek {x:Bind}|Není k dispozici|Podporováno v aplikaci Visual Studio 2019 a novějších verzích|Nepodporováno v aplikaci Visual Studio 2017 nebo předchozích verzích|

## <a name="error-messages"></a>Chybové zprávy

Při použití kódu XAML Hot reload může docházet k následujícím chybám.

|Chybová zpráva|Popis|
|-|-|-|
|Zajistěte selhání události|Chyba znamená, že se pokoušíte o přenos události do některého z vašich ovládacích prvků, které se při spuštění aplikace nepodporují.|
|Úpravy a pokračování jazyka XAML nenalezly žádné prvky, které by bylo možné aktualizovat.|K chybě dojde při úpravách jazyka XAML, který nelze v aplikaci aktualizovat.</br> Tato chyba se může někdy vyřešit pomocí spuštěné aplikace a přejít tak k zobrazení, ve kterém se používá XAML.</br> V některých případech tato chyba znamená, že konkrétní změnu nelze použít, dokud nerestartujete relaci ladění. |
|Tato změna se během relace ladění nepodporuje.|Chyba indikuje, že změna, kterou zkoušíte, není podporována kódováním XAML Hot reloading. Zastavte ladicí relaci, proveďte změnu a pak znovu spusťte ladicí relaci.|
