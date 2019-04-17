---
title: 'CA1903: Použijte pouze API z cíleného rozhraní | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOnlyAPIFromTargetedFramework
- CA1903
helpviewer_keywords:
- UseOnlyApiFromTargetedFramework
- CA1903
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 146563dfa358367e7c22f8ad37564b85d64eaf1d
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59647152"
---
# <a name="ca1903-use-only-api-from-targeted-framework"></a>CA1903: Používejte jen rozhraní API z cílové architektury
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [CA1903: Použijte pouze API z cíleného rozhraní](https://docs.microsoft.com/visualstudio/code-quality/ca1903-use-only-api-from-targeted-framework).  
  
|||  
|-|-|  
|TypeName|UseOnlyApiFromTargetedFramework|  
|CheckId|CA1903|  
|Kategorie|Microsoft.Portability|  
|Narušující změna|Zásadní - při vyvolání s podpisem externě viditelného členu nebo typu.<br /><br /> Bez konce – při vyvolání v těle metody.|  
  
## <a name="cause"></a>Příčina  
 Člen nebo typ používá člen nebo typ, který byl zaveden v aktualizaci service pack, která není součástí cílové rozhraní projektu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Nové členy a typy byly součástí rozhraní .NET Framework 2.0 Service Pack 1 a 2, rozhraní .NET Framework 3.0 Service Pack 1 a 2 a rozhraní .NET Framework 3.5 Service Pack 1. Projekty, které cílí hlavní verze rozhraní .NET Framework neúmyslně může trvat závislosti na těchto nových rozhraní API. Pokud chcete zabránit této závislosti, toto pravidlo je vyvoláno na použití nové členy a typy, které nejsou zahrnuty ve výchozím nastavení se cílové rozhraní projektu.  
  
 **Cílová architektura a závislosti Service Pack**  
  
|||  
|-|-|  
|Pokud je Cílová architektura|Je aktivována na použití členy zavedený|  
|.NET Framework 2.0|Rozhraní .NET framework 2.0 SP1, .NET Framework 2.0 SP2|  
|.NET Framework 3.0|Rozhraní .NET framework 2.0 SP1, .NET Framework 2.0 SP2, rozhraní .NET Framework 3.0 s aktualizací SP1, .NET Framework 3.0 s aktualizací SP2|  
|.NET Framework 3.5|.NET Framework 3.5 SP1|  
|.NET Framework 4|Není k dispozici|  
  
 Chcete-li změnit cílový rámec projektu, [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 K odebírání závislostí pro aktualizace service pack, odeberte všechny použití nového člena nebo typu. Pokud je to rozhodnout vědomě a záměrně závislost, potlačit upozornění nebo vypnout toto pravidlo.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla, pokud to není záměrné závislost na balíčku zadaná služba. V takovém případě se vaše aplikace nemusí podařit spustit v systémech bez této aktualizace service pack nainstalována. Potlačit upozornění nebo vypněte toto pravidlo, pokud jste to byli rozhodnout vědomě a záměrně závislost.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje třídu, která používá typ DateTimeOffset, která je dostupná pouze v rozhraní .NET 2.0 Service Pack 1. Tento příklad vyžaduje, aby byla vybrána rozhraní .NET Framework 2.0 v rozevíracím seznamu cílovou architekturu ve vlastnostech projektu.  
  
 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Portability.UseOnlyApiFromTargetedFramework/CS/FxCop.Portability.UseOnlyApiFromTargetedFramework.cs#1)]  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu řeší dříve popsaná porušení nahrazením použití typu DateTimeOffset typu DateTime.  
  
 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Portability.UseOnlyApiFromTargetedFramework2/CS/FxCop.Portability.UseOnlyApiFromTargetedFramework2.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Upozornění přenositelnosti](../code-quality/portability-warnings.md)   
 [Cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md)
