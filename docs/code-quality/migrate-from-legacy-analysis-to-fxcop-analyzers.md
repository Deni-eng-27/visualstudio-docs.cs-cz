---
title: Migrace z FxCop do zdrojové analýzy (FxCop analyzátory)
ms.custom: SEO-VS-2020
description: Naučte se, jak poprvé analyzovat kód nebo jak migrovat z binární analýzy (FxCop) na nový způsob analýzy spravovaného kódu pomocí analýzy zdrojů (FxCop Analyzer).
ms.date: 03/06/2020
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- FxCop, migration
- legacy analysis, migration
- source code analysis, migration
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cb75b7374e7f88f4643a5ecc4a9c193d8144efc4
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2020
ms.locfileid: "91860474"
---
# <a name="migrate-from-legacy-analysis-fxcop-to-source-analysis-fxcop-analyzers"></a>Migrace ze starší verze Analysis (FxCop) do zdrojové analýzy (FxCop analyzátory)

Analyzátory zdroje podle .NET Compiler Platform ("Roslyn") nahrazují [starší verzi analýzy](../code-quality/code-analysis-for-managed-code-overview.md) spravovaného kódu. Pro novější šablony projektů, jako jsou například .NET Core a .NET Standard projekty, není dostupná starší analýza.

Mnoho pravidel pro starší verzi Analysis (FxCop) již bylo přepsáno pro analyzátory FxCop, což je sada analyzátorů kódu Roslyn. [Analyzátory FxCop nainstalujete jako balíček NuGet](install-fxcop-analyzers.md#nuget-package) , na který se odkazuje v projektu nebo řešení. Analyzátory FxCop spouštějí analýzu založenou na zdrojovém kódu během provádění kompilátoru. Výsledky analyzátoru jsou hlášeny spolu s výsledky kompilátoru.

Další informace o rozdílech mezi staršími verzemi analýzy a analýzou zdroje najdete v následujících tématech:

- [Analýza zdrojového kódu oproti starší analýze](../code-quality/fxcop-analyzers-faq.md#whats-the-difference-between-legacy-fxcop-and-fxcop-analyzers)

- [Nejčastější dotazy týkající se analyzátorů FxCop](../code-quality/fxcop-analyzers-faq.md)

Pokud chcete migrovat na zdrojovou analýzu, [nainstalujte analyzátory FxCop](../code-quality/install-fxcop-analyzers.md). Podobně jako porušení pravidel pro analýzu starších verzí se v okně Seznam chyb v aplikaci Visual Studio zobrazí porušení analýzy zdrojového kódu. Kromě toho se porušení analýzy zdrojového kódu zobrazí také v editoru kódu jako *vlnovky* pod problematickým kódem. Barva vlnovky závisí na [nastavení závažnosti](../code-quality/use-roslyn-analyzers.md#configure-severity-levels) pravidla. Pokud chcete zobrazit stav pravidel, která se přepravují na nové analyzátory FxCop, přečtěte si téma [ported a untransported Rules](../code-quality/fxcop-rule-port-status.md).

Další informace o tom, jak nakonfigurovat analyzátory FxCop:

- Pokud chcete nakonfigurovat analyzátory FxCop, přečtěte si téma [Konfigurace analyzátorů FxCop](/dotnet/fundamentals/code-analysis/code-quality-rule-options).

- Informace o konfiguraci analyzátorů pomocí předdefinovaných pravidel s EditorConfig nebo souborem sady pravidel najdete v tématu [Povolení kategorie pravidel](/dotnet/fundamentals/code-analysis/code-quality-rule-options).
