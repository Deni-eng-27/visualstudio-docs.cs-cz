---
title: "CA1020: Vyvarujte se oborům názvu s několika typy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ae5f1693fc00bca0068d66c20e64655b5f7ea106
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: Vyvarujte se oborům názvu s malým množstvím typů
|||  
|-|-|  
|TypeName|AvoidNamespacesWithFewTypes|  
|CheckId|CA1020|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Obor názvů než globální obor názvů obsahuje méně než pět typů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Ujistěte se, že každý obory má logické organizace, a zda existuje platné důvod uvést typy v řídce vyplněná oboru názvů. Obory názvů by mělo obsahovat typy, které se používají společně ve většině scénářů. Při jejich aplikace se vzájemně vylučují, typy by měl být umístěn v samostatné obory názvů. Například <xref:System.Web.UI> obor názvů obsahuje typy, které se používají ve webových aplikacích a <xref:System.Windows.Forms> obor názvů obsahuje typy, které se používají v [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)]– na základě aplikací. I když oba obory názvů mít typy, které řídí aspektů uživatelské rozhraní, nejsou tyto typy určený k použití ve stejné aplikaci. Proto jsou umístěné v samostatné obory názvů. Pozor, obor názvů organizace může být užitečné také vzhledem k tomu, že jeho hodnota se zvyšuje možnosti rozpoznání funkce. Prověřením hierarchii oboru názvů by mohli najít typy, které implementují funkce příjemci knihovny.  
  
> [!NOTE]
>  Typy návrhu a oprávnění by neměl sloučit jiných oborech názvů pro dosažení souladu s těmito obecnými zásadami. Tyto typy patří ve svých vlastních oborů názvů níže hlavní obor názvů, a musí končit obory názvů `.Design` a `.Permissions`, v uvedeném pořadí.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, pokuste se zkombinovat obory názvů, které obsahují pouze několik typů do jednoho oboru názvů.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné při obor názvů neobsahuje typy, které se používají s typy v jiných obory potlačit upozornění na toto pravidlo.