---
title: 'CA1725: Názvy parametrů by měly odpovídat základní deklaraci'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7e6142ff65800e3d31a867ba0fb1ff63afba187b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54973067"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: Názvy parametrů by měly odpovídat základní deklaraci

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Název parametru v externě viditelné metodě přepsání neodpovídá názvu parametru v základní deklaraci metody nebo název parametru v deklaraci metody rozhraní.

## <a name="rule-description"></a>Popis pravidla
 Konzistentní pojmenování parametrů v hierarchii přetěžování zvyšuje použitelnost přetížení metody. Název parametru, který se v odvozené metodě liší od názvu v základní deklaraci, může způsobit zmatení, zda se u metody jedná o přepis základní metody, nebo o nové přetížení metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přejmenujte parametr odpovídat základní deklaraci. Oprava je zásadní změny pro metody viditelné modelu COM.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla s výjimkou metod viditelné modelu COM v knihovnách, které byly dříve součástí.