---
title: 'CA3006: Zkontrolujte ohrožení zabezpečení injektáží příkazu procesu v kódu'
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
ms.openlocfilehash: 986607d7f42f49c99396bbb021c48bad549930c9
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237282"
---
# <a name="ca3006-review-code-for-process-command-injection-vulnerabilities"></a>CA3006: Zkontrolujte ohrožení zabezpečení injektáží příkazu procesu v kódu

|||
|-|-|
|TypeName|ReviewCodeForProcessCommandInjectionVulnerabilities|
|CheckId|CA3006|
|Kategorie|Microsoft.Security|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne příkazu procesu.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodným vstupem se zaměříte na útoky vkládání příkazů. Útok injektáže příkazu může spustit škodlivé příkazy v podkladovém operačním systému a ohrozit tak zabezpečení a integritu serveru.

Toto pravidlo se pokouší najít vstup z požadavků HTTP, které dosáhnou příkazu procesu.

> [!NOTE]
> Toto pravidlo nemůže sledovat data napříč sestaveními. Například pokud jedno sestavení přečte vstup požadavku HTTP a pak ho předá do jiného sestavení, které spustí proces, toto pravidlo nevytvoří upozornění.

> [!NOTE]
> Existuje konfigurovatelné omezení, jak hluboko bude toto pravidlo analyzovat tok dat napříč voláními metod. Postup konfigurace limitu v souboru EditorConfig naleznete v tématu [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

- Pokud je to možné, vyhněte se spouštění procesů na základě vstupu uživatele.
- Ověří vstup proti známé bezpečné sadě znaků a délky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že vstup byl ověřen nebo byl jeho řídicím znakem zabezpečený, je bezpečné toto upozornění potlačit.

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

```csharp
using System;
using System.Diagnostics;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Process p = Process.Start(input);
    }
}
```

```vb
Imports System
Imports System.Diagnostics

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs as EventArgs)
        Dim input As String = Me.Request.Form("in")
        Dim p As Process = Process.Start(input)
    End Sub
End Class
```
