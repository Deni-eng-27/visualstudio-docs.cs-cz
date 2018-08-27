---
title: 'CA2121: Statické konstruktory by měly být privátní | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6b7052a25df5e736276b458247eb625ab584d473
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902917"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statické konstruktory by měly být privátní
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2121: statické konstruktory by měly být privátní](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private).

|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ má statický konstruktor, který není privátní.

## <a name="rule-description"></a>Popis pravidla
 Statický konstruktor, označované také jako konstruktor třídy, slouží k inicializaci typu. Systém volá statický konstruktor před vytvořením první instance typu nebo předtím, než jsou odkazovány jakékoli statické členy. Uživatel nemá žádnou kontrolu nad tím, kdy je volána statický konstruktor. Pokud statický konstruktor není soukromý, může být volán jiným kódem než kódem systému. V závislosti na operacích, které jsou provedeny v konstruktoru, to může způsobit neočekávané chování.

 Toto pravidlo je vynuceno kompilátory C# a Visual Basic .NET.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Porušení jsou obvykle způsobeno jedním z následujících akcí:

-   Definice statického konstruktoru pro váš typ a nebyly provedeny je privátní.

-   Kompilátor programovacího jazyka přidány výchozí statický konstruktor do typu a nebyly provedeny je privátní.

 Chcete-li vyřešit první druh porušení, soukromá statický konstruktor. Chcete-li vyřešit druhý typ, přidejte privátní statický konstruktor do typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte těchto porušení. Pokud váš návrh softwaru vyžaduje explicitní volání konstruktoru statický konstruktor, je pravděpodobné, že návrh obsahuje závažné chyby a byste měli zkontrolovat.



