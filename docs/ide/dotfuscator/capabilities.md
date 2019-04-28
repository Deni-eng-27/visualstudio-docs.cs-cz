---
title: Funkce Dotfuscatoru
ms.date: 03/28/2019
ms.devlang: dotnet
ms.topic: conceptual
keywords: Nástroj Dotfuscator, nástroj Dotfuscator Community, řešení Dotfuscator CE, PreEmptive, společnosti PreEmptive Solutions PreEmptive ochrany, ochranu, community edition, obfuskace, .NET, bezplatný, Visual Studio 2017, Visual Studio 2019, Visual Studio
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator Community
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: Přečtěte si, že funkce bezplatnou kopii verze nástroje Dotfuscator Community součástí sady Visual Studio.
ms.assetid: 0ee89c58-c900-48fc-a6a2-65ace00e8bab
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5bf42ec3c706282adf2752d21c0c121f89c2ed5f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62557252"
---
# <a name="capabilities-of-dotfuscator"></a>Funkce Dotfuscatoru

Tato stránka se zaměřuje na funkce řešení Dotfuscator Community se některé odkazy na rozšířené možnosti, které jsou k dispozici prostřednictvím [upgrady][upgrades].

Nástroj Dotfuscator Community je *po sestavení* systému pro aplikace .NET.
S ním, budou moct uživatelé sady Visual Studio [obfuskaci sestavení] [ obfuscation] a vložit [aktivní defense opatření] [ checks] do aplikace - všechny bez nutnosti přístupu k původní zdrojový kód nástroje Dotfuscator.
Nástroj Dotfuscator chrání vaši aplikaci několika různými způsoby vytváření strategie vrstvami ochrany.

Nástroj Dotfuscator Community podporuje a široký rozsah .NET sestavení a aplikace typy, včetně [univerzální platformu Windows (UPW)] [ uwp] a [Xamarin] [ xamarin].

## <a name="intellectual-property-protection"></a>Ochranu duševního vlastnictví

Návrh, chování a implementaci vaší aplikace jsou formy duševní vlastnictví (IP).
Aplikace vytvořené pro rozhraní .NET Framework jsou však v podstatě otevře knih; je velmi snadné sestavení .NET zpětné analýzy, [obsahují základní metadata a mezikódu][assemblies].

Nástroj Dotfuscator Community zahrnuje základní [.NET obfuskace] [ obfuscation] ve formě [přejmenování][renaming].
Ke zdrojovému kódu prostřednictvím zpětné analýzy, že maskuje svůj kód pomocí nástroje Dotfuscator snižuje riziko neoprávněného přístupu, jako důležité informace o názvech už být veřejné.
Obfuskace také zobrazuje úsilí na druhé straně k ochraně vašeho kódu z zkoumání - cenné krok při vytváření, že je vaše IP adresa ze zákona chráněný jako tajemství.

Mnoho [funkcí ochrany aplikací integrity](#application-integrity-protection) nástroje Dotfuscator Community další brání zpětná analýza.
Chybný actor například může pokusit připojit ladicí program ke spuštěné instanci vaší aplikace, chcete-li pochopit programovou logiku.
Nástroje Dotfuscator můžete vložit [proti ladění chování][debug] do vaší aplikace to bránit.

## <a name="application-integrity-protection"></a>Ochrana Integrity aplikace

Kromě ochrany zdrojového kódu, je také důležité zajistit, že vaše aplikace se používá tak, jak navrženo.
Útočníci se mohou pokusit o zneužití vaší aplikace, aby bylo možné obejít licenční zásady (tj, softwarové pirátství), krádeži nebo citlivá data, jakým aplikace zpracovává manipulaci s, nebo chcete změnit chování aplikace.

Nástroj Dotfuscator Community můžete vložit [kód pro ověření aplikace] [ checks] do vašeho sestavení, včetně [boj proti][tamper], [proti ladění][debug], a [proti rootem] [ root] míry.
Když je zjištěn stav Neplatná aplikace, můžete kód pro ověření [zvát kódu aplikace k vyřešení situace vhodným způsobem][check-app].
Nebo, pokud nechcete napsat kód, který používá neplatný popisovač aplikace, nástroje Dotfuscator můžete také vložit [odpovědi][check-action] chování, aniž by bylo nutné žádné úpravy zdrojového kódu.

Mnohé z těchto stejné metody mohou také používá k vynucení [ukončenou životností termíny][shelflife] pro vyhodnocení nebo zkušební verze softwaru.

## <a name="see-also"></a>Viz také

[Toto téma v uživatelské příručce nástroje úplné řešení Dotfuscator Community][full]

<!-- Copyright © 2019 PreEmptive Solutions, LLC -->

[assemblies]:  https://docs.microsoft.com/dotnet/standard/assembly-format
[uwp]:  https://www.preemptive.com/blog/article/856-uwp-applications-in-dotfuscator-ce/91-dotfuscator-ce
[xamarin]:  https://www.preemptive.com/obfuscating-xamarin-with-dotfuscator

[upgrades]:  upgrades.md

[obfuscation]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_overview.html
[renaming]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[checks]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[check-app]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#app-notification
[check-action]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#action

[tamper]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[root]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_root.html
[shelflife]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_capabilities.html
