---
title: 'CA3004: Prohlédněte si kód pro zveřejnění informace o ohrožení zabezpečení'
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
ms.openlocfilehash: 82f763d9a6b1ec27975aa80054456a6bbbaeaa2b
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018802"
---
# <a name="ca3004-review-code-for-information-disclosure-vulnerabilities"></a>CA3004: Prohlédněte si kód pro zveřejnění informace o ohrožení zabezpečení

|||
|-|-|
|TypeName|ReviewCodeForInformationDisclosureVulnerabilities|
|CheckId|CA3004|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Zprávu výjimky, trasování zásobníku nebo řetězcové vyjádření dosáhne webové výstup.

## <a name="rule-description"></a>Popis pravidla

Zveřejnění informací o výjimce poskytuje přehled o tom, interních dat vaší aplikace, který může pomoct útočníci najít další chyby zneužít útočníci.

Toto pravidlo se pokusí najít zpráva o výjimce, trasování zásobníku nebo řetězcové vyjádření se výstup do odpovědi HTTP.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení zachytí výjimku a předává je na jiné sestavení, jejichž výstupem jsou výjimky, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v `.editorconfig` soubory.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Není výstupní informace o výjimce do odpovědi protokolu HTTP. Místo toho poskytují obecné chybové zprávy. Zobrazit [OWASP pro zpracování chyb stránky](https://www.owasp.org/index.php/Error_Handling) další pokyny.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud znáte webové výstup je v rámci hranice vztahů důvěryhodnosti vaší aplikace a nikdy nezveřejní, je možné pro potlačení tohoto upozornění. Je to vzácný. Vzít v úvahu, že hranice vztahů důvěryhodnosti vaší aplikace a toky dat může postupem času změnit.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write(e.ToString());
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write(e.ToString())
        End Try
    End Sub
End Class
```

### <a name="solution"></a>Řešení

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write("An error occurred. Please try again later.");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write("An error occurred. Please try again later.")
        End Try
    End Sub
End Class
```