---
title: 'CA1812: Vyhněte se nevytváření instancí vnitřních tříd | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
caps.latest.revision: 28
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f5a36ee8cffc221d15243ff72e2e71558e867319
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72645399"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Kategorie|Microsoft. Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Instance typu na úrovni sestavení není vytvořena kódem v sestavení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo se pokusí vyhledat volání jednoho z konstruktorů typu a oznámí porušení, pokud není nalezeno žádné volání.

 Toto pravidlo nezkoumá následující typy:

- Typy hodnot

- Abstraktní typy

- Výčty

- Delegáty

- Typy polí generovaných kompilátorem

- Typy, jejichž instance se nedají vytvořit a které definují `static` (`Shared` pouze v Visual Basic).

  Použijete-li <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> na sestavení, které je analyzováno, toto pravidlo nebude provedeno na žádném konstruktoru, který je označen jako `internal`, protože nemůžete určit, zda je pole používáno jiným `friend`m sestavením.

  I když nemůžete toto omezení obejít [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] analýze kódu, externí samostatné FxCop proběhne na vnitřních konstruktorech, pokud je v analýze přítomno každé `friend` sestavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte typ nebo přidejte kód, který ho používá. Pokud typ obsahuje pouze statické metody, přidejte jeden z následujících typů do typu, čímž zabráníte kompilátoru v generování výchozího veřejného konstruktoru instance:

- Privátní konstruktor pro typy, které cílí na [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze 1,0 a 1,1.

- Modifikátor `static` (`Shared` in Visual Basic) pro typy, které cílí na [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Z tohoto pravidla je bezpečné potlačit upozornění. Toto upozornění doporučujeme potlačit v následujících situacích:

- Třída je vytvořena pomocí metod reflexe s pozdní vazbou, jako je <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

- Třída je vytvořena automaticky modulem runtime nebo [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Například třídy, které implementují <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> nebo <xref:System.Web.IHttpHandler?displayProperty=fullName>.

- Třída je předána jako parametr obecného typu, který má nové omezení. Například následující příklad vyvolá toto pravidlo.

  ```csharp
  internal class MyClass
  {
      public DoSomething()
      {
      }
  }
  public class MyGeneric<T> where T : new()
  {
      public T Create()
      {
          return new T();
      }
  }
  // [...]
  MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
  mc.Create();
  ```

  V těchto situacích doporučujeme toto upozornění potlačit.

## <a name="related-rules"></a>Související pravidla
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)
