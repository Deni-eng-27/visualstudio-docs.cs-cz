---
title: Upozornění analýzy kódu pro spravovaný kód | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vc.project.vcfxcoptool.enablefxcop
helpviewer_keywords:
- managed code analyis, warnings
- warnings, managed code analysis
- managed code analysis warnings
- code analysis,managed code
ms.assetid: 3c2741ff-0d3a-42e6-acd5-d42310bd03c4
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fddcff8bb51216097689a86bd25718a0727c2b45
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672938"
---
# <a name="code-analysis-for-managed-code-warnings"></a>Upozornění Analýzy kódu pro spravovaný kód
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nástroj Analýza spravovaného kódu poskytuje upozornění indikující porušení pravidel ve spravovaných knihovnách kódu. Upozornění se uspořádají do oblastí pravidla, jako je návrh, lokalizace, výkon a zabezpečení. Každé upozornění znamená porušení pravidla analýzy spravovaného kódu. Tato část poskytuje podrobné diskuze a příklady pro každé upozornění analýzy spravovaného kódu.

 V následující tabulce je uveden typ informací, které jsou k dispozici pro každé upozornění.

|Položkami|Popis|
|----------|-----------------|
|Typ|Název TypeName pro pravidlo|
|CheckId|Jedinečný identifikátor pravidla CheckId a kategorie se používají pro potlačení varování ve zdrojovém zobrazení.|
|Kategorie|Kategorie upozornění|
|Narušující změna|Zda je oprava pro porušení pravidla zásadní změnou. Zásadní změna znamená, že sestavení, které má závislost na cíli, který způsobil porušení, nebude znovu zkompilováno s novou opravenou verzí nebo může v době běhu selhat z důvodu změny. Je-li k dispozici více oprav a nejméně jedna oprava je zásadní změna a jedna oprava není, je určena možnost "průlom" i "nemožnost".|
|příčina|Konkrétní spravovaný kód, který způsobí, že pravidlo vygeneruje upozornění.|
|Popis|Popisuje problémy, které jsou za upozorněním.|
|Jak vyřešit porušení|Vysvětluje, jak změnit zdrojový kód pro splnění pravidla a zabránit tomu, aby vygenerovalo upozornění.|
|Kdy potlačit upozornění|Popisuje, kdy je bezpečné potlačit upozornění od pravidla.|
|Příklad kódu|Příklady, které porušují pravidlo a opravené příklady, které splňují pravidlo.|
|Související upozornění|Související upozornění.|

## <a name="in-this-section"></a>V tomto oddílu

|||
|-|-|
|[Upozornění podle CheckId](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)|Zobrazí všechna upozornění podle CheckId|
|[Upozornění kryptografie](../code-quality/cryptography-warnings.md)|Upozornění, která podporují bezpečnější knihovny a aplikace přes správné použití kryptografie.|
|[Upozornění ohledně návrhu](../code-quality/design-warnings.md)|Upozornění podporující správný návrh knihovny podle pokynů pro návrh [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].|
|[Upozornění globalizace](../code-quality/globalization-warnings.md)|Upozornění, která podporují knihovny a aplikace připravené pro použití ve světě.|
|[Upozornění interoperability](../code-quality/interoperability-warnings.md)|Upozornění podporující interakci s klienty modelu COM.|
|[Upozornění udržovatelnosti](../code-quality/maintainability-warnings.md)|Upozornění, která podporují údržbu knihovny a aplikace.|
|[Upozornění mobility](../code-quality/mobility-warnings.md)|Upozornění, která podporují efektivní využití výkonu.|
|[Upozornění na pojmenování](../code-quality/naming-warnings.md)|Upozornění, která podporují dodržování zásad vytváření názvů [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] pokynů pro návrh|
|[Upozornění výkonu](../code-quality/performance-warnings.md)|Upozornění, která podporují vysoce výkonné knihovny a aplikace.|
|[Upozornění přenositelnosti](../code-quality/portability-warnings.md)|Upozornění, která podporují přenositelnost napříč různými platformami.|
|[Upozornění spolehlivosti](../code-quality/reliability-warnings.md)|Upozornění, která podporují spolehlivost knihovny a aplikace, jako je třeba správné využití paměti a vlákna.|
|[Upozornění zabezpečení](../code-quality/security-warnings.md)|Upozornění, která podporují bezpečnější knihovny a aplikace.|
|[Upozornění využití](../code-quality/usage-warnings.md)|Upozornění, která podporují příslušné použití [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].|
|[Chyby zásad Analýzy kódu](../code-quality/code-analysis-policy-errors.md)|Chyby, ke kterým dojde, pokud není při vrácení se změnami splněna zásada analýzy kódu.|
