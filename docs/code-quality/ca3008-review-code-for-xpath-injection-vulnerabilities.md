---
title: 'CA3008: Zkontrolujte ohrožení zabezpečení injektáží XPath v kódu'
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
ms.openlocfilehash: 1d001dc306bbb225c4ecc1c0f17bf46619e2d0a7
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237265"
---
# <a name="ca3008-review-code-for-xpath-injection-vulnerabilities"></a>CA3008: Zkontrolujte ohrožení zabezpečení injektáží XPath v kódu

|||
|-|-|
|TypeName|ReviewCodeForXPathInjectionVulnerabilities|
|CheckId|CA3008|
|Kategorie|Microsoft.Security|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne dotazu XPath.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodným vstupem si vědomete útoků prostřednictvím injektáže XPath. Vytváření dotazů XPath pomocí nedůvěryhodného vstupu může útočníkovi umožnit škodlivým způsobem manipulovat s dotazem, aby vrátil nezamýšlený výsledek a případně vyzradit obsah dotazovaného XML.

Toto pravidlo se pokouší najít vstup z požadavků HTTP, které dosáhly výrazu XPath.

> [!NOTE]
> Toto pravidlo nemůže sledovat data napříč sestaveními. Například pokud jedno sestavení přečte vstup požadavku HTTP a pak ho předává do jiného sestavení, které provádí dotaz XPath, toto pravidlo nevytvoří upozornění.

> [!NOTE]
> Existuje konfigurovatelné omezení, jak hluboko bude toto pravidlo analyzovat tok dat napříč voláními metod. Postup konfigurace limitu v souboru EditorConfig naleznete v tématu [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Některé přístupy k opravám ohrožení zabezpečení vkládání XPath zahrnují:

- Nevytvářejte dotazy XPath ze vstupu uživatele.
- Ověřte, zda vstup obsahuje pouze bezpečnou sadu znaků.
- Řídicí uvozovky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že jste ověřili, že vstup je bezpečný, je v pořádku Toto upozornění potlačit.

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

```csharp
using System;
using System.Xml.XPath;

public partial class WebForm : System.Web.UI.Page
{
    public XPathNavigator AuthorizedOperations { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string operation = Request.Form["operation"];

        // If an attacker uses this for input:
        //     ' or 'a' = 'a
        // Then the XPath query will be:
        //     authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        // and it will return any authorizedOperation node.
        XPathNavigator node = AuthorizedOperations.SelectSingleNode(
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']");
    }
}
```

```vb
Imports System
Imports System.Xml.XPath

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Public Property AuthorizedOperations As XPathNavigator

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim operation As String = Me.Request.Form("operation")

        ' If an attacker uses this for input:
        '     ' or 'a' = 'a
        ' Then the XPath query will be:
        '      authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        ' and it will return any authorizedOperation node.
        Dim node As XPathNavigator = AuthorizedOperations.SelectSingleNode( _
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']")
    End Sub
End Class
```
