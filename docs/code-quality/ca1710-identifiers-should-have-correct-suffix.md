---
title: 'CA1710: Identifikátory by měly mít správnou příponu'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50c67c614c4ece8f1925f4133f749a1c5747fe31
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234172"
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: Identifikátory by měly mít správnou příponu

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectSuffix|
|CheckId|CA1710|
|Kategorie|Microsoft.Naming|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Identifikátor nemá správnou příponu.

Ve výchozím nastavení toto pravidlo vypadá pouze na externě viditelných identifikátorech, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Podle konvence mají názvy typů, které rozšíří určité základní typy nebo které implementují určitá rozhraní nebo typy odvozené z těchto typů, příponu, která je přidružena k základnímu typu nebo rozhraní.

Zásady vytváření názvů poskytují běžný vzhled pro knihovny, které cílí na modul CLR (Common Language Runtime). Tím se zmenší výuková křivka, která je požadována pro nové knihovny softwaru, a zvyšuje důvěru zákazníků, že knihovna byla vyvinuta někým, kdo má zkušenosti s vývojem spravovaného kódu.

Následující tabulka uvádí základní typy a rozhraní, které mají přidružené přípony.

|Základní typ/rozhraní|Auditování|
|--------------------------|------------|
|<xref:System.Attribute?displayProperty=fullName>|Atribut|
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|
|<xref:System.Exception?displayProperty=fullName>|Výjimka|
|<xref:System.Collections.ICollection?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Slovníku|
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.Queue?displayProperty=fullName>|Kolekce nebo fronta|
|<xref:System.Collections.Stack?displayProperty=fullName>|Kolekce nebo zásobník|
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|Shromažďování|
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Slovníku|
|<xref:System.Data.DataSet?displayProperty=fullName>|DataSet|
|<xref:System.Data.DataTable?displayProperty=fullName>|Kolekce nebo DataTable|
|<xref:System.IO.Stream?displayProperty=fullName>|Stream|
|<xref:System.Security.IPermission?displayProperty=fullName>|Oprávnění|
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|Podmínka|
|Delegát obslužné rutiny události.|EventHandler|

Typy, které <xref:System.Collections.ICollection> implementují a jsou zobecněný typ datové struktury, jako je slovník, zásobník nebo fronta, jsou povoleny názvy, které poskytují smysluplnější informace o zamýšleném využití typu.

Typy, které <xref:System.Collections.ICollection> implementují a jsou kolekce konkrétních položek, mají názvy končící slovem ' Collection '. Například kolekce <xref:System.Collections.Queue> objektů by měla mít název QueueCollection. Přípona ' Collection ' znamená, že členy kolekce lze vyčíslit pomocí `foreach` příkazu (`For Each` in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

Typy, které <xref:System.Collections.IDictionary> implementují názvy končící slovem Dictionary, i když typ také implementuje <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.ICollection>. Konvence pojmenování přípon kolekcí a slovníku umožňují uživatelům rozlišovat následující dva vzory výčtu.

Typy s příponou Collection se řídí tímto vzorem výčtu.

```
foreach(SomeType x in SomeCollection) { }
```

Typy s příponou Dictionary následují po tomto vzoru výčtu.

```
foreach(SomeType x in SomeDictionary.Values) { }
```

Objekt se skládá z <xref:System.Data.DataTable> kolekce objektů, <xref:System.Data.DataColumn?displayProperty=fullName> které se skládají z kolekcí objektů a <xref:System.Data.DataRow?displayProperty=fullName> , mimo jiné. <xref:System.Data.DataSet> Tyto kolekce jsou <xref:System.Collections.ICollection> implementovány prostřednictvím <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> základní třídy.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Přejmenujte typ tak, aby se najmenoval správným termínem.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud je typ zobecněnou datovou strukturou, která může být rozšířená nebo která bude obsahovat libovolnou sadu různých položek, je bezpečné potlačit upozornění na použití přípony kolekce. V tomto případě je název, který poskytuje smysluplné informace o implementaci, výkonu nebo dalších vlastnostech struktury dat, smyslem (například BinaryTree). V případech, kdy typ představuje kolekci konkrétního typu (například StringCollection), potlačíte upozornění z tohoto pravidla, protože přípona označuje, že typ lze vytvořit pomocí `foreach` příkazu.

U jiných přípon potlačíte upozornění z tohoto pravidla. Přípona umožňuje, aby bylo zamýšlené použití zřejmé z názvu typu.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1710.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (pojmenování). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

[CA1711: Identifikátory by neměly mít nesprávnou příponu](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
- [Zpracování a vyvolávání událostí](/dotnet/standard/events/index)