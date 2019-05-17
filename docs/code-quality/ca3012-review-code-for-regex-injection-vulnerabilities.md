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
ms.openlocfilehash: b66e28804e85b04b1492a20828c42a9b5efd3cf8
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841041"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012: Zkontrolujte ohrožení zabezpečení injektáží regulárního výrazu v kódu

|||
|-|-|
|TypeName|ReviewCodeForRegexInjectionVulnerabilities|
|CheckId|CA3012|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne regulární výraz.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, dávejte útoků prostřednictvím injektáže regulární výraz. Útočník může pomocí regulárního výrazu vkládání speciálně upravují regulární výraz, aby regulární výraz odpovídat neočekávaným výsledkům nebo aby regulární výraz spotřebovat nadměrné využití procesoru, výsledkem je útok DoS.

Toto pravidlo se pokusí najít vstup požadavků HTTP dosažení regulární výraz.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, která vytvoří regulárního výrazu, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v souboru EditorConfig.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Některá zmírnění rizik proti regulární výraz injektáže patří:

- Vždy používat [odpovídat vypršení časového limitu](/dotnet/standard/base-types/best-practices#use-time-out-values) při používání regulárních výrazů.
- Vyhněte se použití regulárních výrazů, které jsou založeny na vstup uživatele.
- Řídicí znaky ze vstupu uživatele voláním <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName> nebo jiným způsobem.
- Povolíte pouze speciální znaky ze vstupu uživatele.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že používáte [odpovídat vypršení časového limitu](/dotnet/standard/base-types/best-practices#use-time-out-values) a uživatelský vstup je zdarma speciální znaky, je to v pořádku pro potlačení tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

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
