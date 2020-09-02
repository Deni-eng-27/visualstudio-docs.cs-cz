---
title: 'CA2118: Kontrola využití SuppressUnmanagedCodeSecurityAttribute | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bc0e88265245d795697d32a9e6a95909c0415259
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538655"
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: Zkontrolujte použití SuppressUnmanagedCodeSecurityAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejný nebo chráněný typ nebo člen má <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> mění výchozí chování zabezpečení systému pro členy, kteří spouštějí nespravovaný kód pomocí zprostředkovatele komunikace s objekty COM nebo vyvolání platformy. Obecně platí, že systém vytváří [data a modelování](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6) pro oprávnění nespravovaného kódu. K této poptávce dochází v době běhu pro každé vyvolání člena a kontroluje každého volajícího v zásobníku volání pro oprávnění. Když je přítomen atribut, systém vytvoří [odkaz](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) pro příslušné oprávnění: oprávnění bezprostředního volajícího je kontrolováno, pokud je volající kompilátor JIT zkompilován.

 Tento atribut slouží především ke zvýšení výkonu, ačkoliv nárůst výkonu může být spojen s významnými riziky zabezpečení. Pokud umístíte atribut na veřejné členy, kteří volají nativní metody, volající v zásobníku volání (Kromě bezprostředního volajícího) nepotřebují oprávnění nespravovaného kódu pro spuštění nespravovaného kódu. V závislosti na akcích veřejného člena a zpracování vstupu může být nedůvěryhodným volajícím umožněn přístup k funkcím, které jsou normálně omezené na důvěryhodný kód.

 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]Spoléhá na kontroly zabezpečení, aby zabránil volajícímu v získání přímého přístupu k adresnímu prostoru aktuálního procesu. Vzhledem k tomu, že tento atribut obchází normální zabezpečení, váš kód představuje vážnou hrozbu, pokud jej lze použít ke čtení nebo zápisu do paměti procesu. Všimněte si, že riziko není omezeno na metody, které úmyslně poskytují přístup ke zpracování paměti; je také k dispozici v jakémkoli scénáři, kde může škodlivý kód dosáhnout přístupu jakýmkoli způsobem, například zadáním překvapivé, poškozeného nebo neplatného vstupu.

 Výchozí zásada zabezpečení neuděluje oprávnění nespravovaného kódu pro sestavení, pokud není prováděna z místního počítače nebo je členem jedné z následujících skupin:

- Skupina kódu zóny počítače

- Skupina kódu se silným názvem Microsoftu

- Skupina kódu silného názvu ECMA

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pečlivě zkontrolujte kód a ujistěte se, že je tento atribut nezbytný. Pokud nejste obeznámeni se zabezpečením spravovaného kódu nebo nerozumíte dopadům na zabezpečení při použití tohoto atributu, odeberte ho z kódu. Pokud je atribut požadován, je nutné zajistit, aby volající nemohly používat váš kód škodlivě. Pokud váš kód nemá oprávnění ke spuštění nespravovaného kódu, tento atribut nemá žádný vliv a měl by být odebrán.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Chcete-li bezpečně potlačit upozornění z tohoto pravidla, je nutné zajistit, aby váš kód neposkytoval volajícím přístup k nativním operacím nebo prostředkům, které lze použít destruktivním způsobem.

## <a name="example"></a>Příklad
 Následující příklad narušuje pravidlo.

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesDoNotSuppress/cs/FxCop.Security.TypesDoNotSuppress.cs#1)]

## <a name="example"></a>Příklad
 V následujícím příkladu `DoWork` Metoda poskytuje veřejně přístupný cestu kódu k metodě vyvolání platformy `FormatHardDisk` .

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PInvokeAndSuppress/cs/FxCop.Security.PInvokeAndSuppress.cs#1)]

## <a name="example"></a>Příklad
 V následujícím příkladu způsobí veřejná metoda `DoDangerousThing` porušení. Pro vyřešení porušení `DoDangerousThing` by měla být soukromá a přístup k ní by měl být prostřednictvím veřejné metody zabezpečené požadavkem zabezpečení, jak je znázorněno v `DoWork` metodě.

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypeInvokeAndSuppress/cs/FxCop.Security.TypeInvokeAndSuppress.cs#1)]

## <a name="see-also"></a>Viz také
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>[Zásady zabezpečeného kódování pravidla](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [optimalizace zabezpečení](https://msdn.microsoft.com/cf255069-d85d-4de3-914a-e4625215a7c0) [data a modelování](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6) [požadavky propojení](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
