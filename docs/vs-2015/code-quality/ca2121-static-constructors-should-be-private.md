---
title: 'CA2121: statické konstruktory by měly být privátní | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7f95b33e1391ca755a6c0df261fa2bd05bd3c7a0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85544310"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statické konstruktory by měly být privátní
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Typ má statický konstruktor, který není privátní.

## <a name="rule-description"></a>Popis pravidla
 Statický konstruktor, označovaný také jako konstruktor třídy, slouží k inicializaci typu. Systém volá statický konstruktor před vytvořením první instance typu nebo předtím, než jsou odkazovány jakékoli statické členy. Uživatel nemá žádné řízení při volání statického konstruktoru. Pokud statický konstruktor není soukromý, může být volán jiným kódem než kódem systému. V závislosti na operacích, které jsou provedeny v konstruktoru, to může způsobit neočekávané chování.

 Toto pravidlo je vynutilo kompilátory C# a Visual Basic .NET.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Porušení jsou obvykle způsobena některou z následujících akcí:

- Definovali jste statický konstruktor pro váš typ a nevytvořili jste ho jako privátní.

- Kompilátor programovacího jazyka přidal do typu výchozí statický konstruktor a nevytvořil ho jako soukromý.

  Chcete-li opravit první druh porušení, nastavte svůj statický konstruktor jako soukromý. Chcete-li opravit druhý druh, přidejte do typu privátní statický konstruktor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Tato porušení potlačíte. Pokud váš návrh softwaru vyžaduje explicitní volání statického konstruktoru, je pravděpodobně návrh obsahuje závažné nedostatky a měl by být přezkoumán.
