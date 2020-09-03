---
title: 'CA2105: pole polí by neměla být jen pro čtení | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: db52bf869642a5bdcc28eeb0792b295ae314a508
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538668"
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105: Pole s poli by neměla být pouze pro čtení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|ArrayFieldsShouldNotBeReadOnly|
|CheckId|CA2105|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejné nebo chráněné pole, které obsahuje pole, je deklarované jen pro čtení.

## <a name="rule-description"></a>Popis pravidla
 Když použijete `readonly` Modifikátor ( `ReadOnly` in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) na pole, které obsahuje pole, nelze změnit pole tak, aby odkazovalo na jiné pole. Avšak prvky pole, které jsou uloženy v poli určeném jen pro čtení, mohou být změněny. Kód, který provádí rozhodnutí nebo provádí operace založené na prvcích pole určeného jen pro čtení, které může být veřejně přístupný, může obsahovat zneužitou chybu zabezpečení.

 Uvědomte si, že pokud máte veřejné pole také v rozporu s pravidlem návrhu [CA1051: Nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit chybu zabezpečení, která je identifikována tímto pravidlem, nespoléhejte na obsah pole jen pro čtení, které může být veřejně přístupné. Důrazně doporučujeme použít jeden z následujících postupů:

- Nahraďte pole kolekcí silného typu, kterou nelze změnit. Další informace naleznete v tématu <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>.

- Nahraďte veřejné pole metodou, která vrací klon soukromého pole. Vzhledem k tomu, že váš kód nespoléhá na klonování, neexistuje nebezpečí, pokud jsou prvky změněny.

  Pokud jste zvolili druhý přístup, neměňte pole pomocí vlastnosti; vlastnosti, které vracejí pole nepříznivě ovlivňující výkon. Další informace najdete v tématu [CA1819: vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Vyloučení upozornění z tohoto pravidla se důrazně nedoporučuje. Téměř žádné scénáře nevzniká, pokud obsah pole jen pro čtení není neimportované. Pokud se jedná o případ s vaším scénářem, odeberte `readonly` Modifikátor místo vyloučení zprávy.

## <a name="example"></a>Příklad
 Tento příklad ukazuje nebezpečí porušení tohoto pravidla. První část ukazuje příklad knihovny, která má typ, `MyClassWithReadOnlyArrayField` , který obsahuje dvě pole ( `grades` a `privateGrades` ), která nejsou zabezpečená. Pole `grades` je veřejné, a proto je zranitelné pro libovolného volajícího. Pole `privateGrades` je privátní, ale je stále zranitelné, protože je vráceno volajícím pomocí `GetPrivateGrades` metody. `securePrivateGrades`Pole je vystaveno bezpečným způsobem pomocí `GetSecurePrivateGrades` metody. Deklarace je deklarovaná jako soukromá, aby sledovala dobré postupy návrhu. Druhá část zobrazuje kód, který mění hodnoty uložené v `grades` `privateGrades` členech a.

 Ukázková knihovna tříd se zobrazí v následujícím příkladu.

 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.ArrayFieldsNotReadOnly/cs/FxCop.Security.ArrayFieldsNotReadOnly.cs#1)]

## <a name="example"></a>Příklad
 Následující kód používá ukázkovou knihovnu tříd k ilustraci problémů zabezpečení pole jen pro čtení.

 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestArrayFieldsRead/cs/FxCop.Security.TestArrayFieldsRead.cs#1)]

 Výstup z tohoto příkladu je:

 **Před manipulací: třídy: 90, 90, 90 privátních stupňů: 90, 90, 90 Secure jakostní třídy, 90, 90, 90** 
 **Po manipulaci: třídy: 90, 555, 90 privátních stupňů: 90, 555, 90 Secure jakostní třídy, 90, 90, 90**
## <a name="see-also"></a>Viz také
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
