---
title: 'CA3012: Zkontrolujte ohrožení zabezpečení injektáží regulárního výrazu v kódu'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 42808b3961b18a23f594800f9d0782c908c9b1ba
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237182"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012: Zkontrolujte ohrožení zabezpečení injektáží regulárního výrazu v kódu

|||
|-|-|
|TypeName|ReviewCodeForRegexInjectionVulnerabilities|
|CheckId|CA3012|
|Kategorie|Microsoft.Security|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne regulárního výrazu.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodným vstupem nezapomeňte na útoky pomocí injektáže regulárního výrazu. Útočník může použít injektáže regulárního výrazu pro zlomyslnou úpravu regulárního výrazu, aby regulární výraz odpovídal nezamýšleným výsledkům, nebo aby regulární výraz využil nadměrného využití procesoru, což způsobuje útok na útok DOS.

Toto pravidlo se pokouší najít vstup z požadavků HTTP, které dosáhnou regulárního výrazu.

> [!NOTE]
> Toto pravidlo nemůže sledovat data napříč sestaveními. Například pokud jedno sestavení přečte vstup požadavku HTTP a pak ho předává do jiného sestavení, které vytvoří regulární výraz, toto pravidlo nevytvoří upozornění.

> [!NOTE]
> Existuje konfigurovatelné omezení, jak hluboko bude toto pravidlo analyzovat tok dat napříč voláními metod. Postup konfigurace limitu v souboru EditorConfig naleznete v tématu [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Některá zmírnění proti injektáže regulárního výrazu zahrnují:

- Při použití regulárních výrazů vždy použít [časový limit shody](/dotnet/standard/base-types/best-practices#use-time-out-values) .
- Nepoužívejte regulární výrazy založené na vstupu uživatele.
- Řídicí znaky speciálních znaků od vstupu uživatele zavoláním <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName> nebo jiné metody.
- Povolí pouze nespeciální znaky ze vstupu uživatele.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že používáte [časový limit shody](/dotnet/standard/base-types/best-practices#use-time-out-values) a vstup uživatele není ve speciálních znacích, je dobré toto upozornění potlačit.

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

```csharp
using System;
using System.Text.RegularExpressions;

public partial class WebForm : System.Web.UI.Page
{
    public string SearchableText { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string findTerm = Request.Form["findTerm"];
        Match m = Regex.Match(SearchableText, "^term=" + findTerm);
    }
}
```

```vb
Imports System
Imports System.Text.RegularExpressions

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Public Property SearchableText As String

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim findTerm As String = Request.Form("findTerm")
        Dim m As Match = Regex.Match(SearchableText, "^term=" + findTerm)
    End Sub
End Class
```
