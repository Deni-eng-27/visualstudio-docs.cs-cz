---
title: 'CA3003: Zkontrolujte ohrožení zabezpečení injektáží cesty k souboru v kódu'
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
ms.openlocfilehash: c9e43dcdf1e923cb7bc4a98b17fd0be71b7927eb
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237403"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003: Zkontrolujte ohrožení zabezpečení injektáží cesty k souboru v kódu

|||
|-|-|
|TypeName|ReviewCodeForFilePathInjectionVulnerabilities|
|CheckId|CA3003|
|Kategorie|Microsoft.Security|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne cesty operace se souborem.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodným vstupem z webových požadavků nezapomeňte při zadávání cest k souborům použít vstup, který je řízený uživatelem. Útočník může číst nezamýšlený soubor, což má za následek zpřístupnění citlivých dat. Nebo může útočník zapisovat do nezamýšleného souboru, což by způsobilo neoprávněnou úpravu citlivých dat nebo narušit zabezpečení serveru. Běžný technik útočníka je [procházení cest](https://www.owasp.org/index.php/Path_Traversal) pro přístup k souborům mimo určený adresář.

Toto pravidlo se pokouší najít vstup z požadavků HTTP, které dosáhly cesty v operaci souboru.

> [!NOTE]
> Toto pravidlo nemůže sledovat data napříč sestaveními. Například pokud jedno sestavení přečte vstup požadavku HTTP a pak ho předává do jiného sestavení, které zapisuje do souboru, toto pravidlo nevytvoří upozornění.

> [!NOTE]
> Existuje konfigurovatelné omezení, jak hluboko bude toto pravidlo analyzovat tok dat napříč voláními metod. Postup konfigurace limitu v souboru EditorConfig naleznete v tématu [Configuration Analyzer](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

- Pokud je to možné, omezte cesty k souborům na základě vstupu uživatele na explicitně známý bezpečný seznam.  Například pokud vaše aplikace potřebuje přístup k "Red. txt", "zeleně. txt" nebo "Blue. txt", povolte pouze tyto hodnoty.
- Zkontrolujte nedůvěryhodné názvy souborů a ověřte, zda je název správně vytvořen.
- Při zadávání cest Používejte názvy úplných cest.
- Vyhněte se potenciálně nebezpečným konstrukcím, jako jsou proměnné prostředí PATH.
- Akceptuje pouze dlouhé názvy souborů a ověří dlouhé jméno, pokud uživatel odesílá krátké názvy.
- Omezí vstup koncového uživatele na platné znaky.
- Zamítnout názvy, kde se překročila délka názvu MAX_PATH
- Zpracuje názvy souborů doslova bez interpretace.
- Určete, zda název souboru představuje soubor nebo zařízení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud jste ověřili vstup, jak je popsáno v předchozí části, je to v pořádku, abyste toto upozornění potlačili.

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userInput = Request.Params["UserInput"];
        // Assume the following directory structure:
        //   wwwroot\currentWebDirectory\user1.txt
        //   wwwroot\currentWebDirectory\user2.txt
        //   wwwroot\secret\allsecrets.txt
        // There is nothing wrong if the user inputs:
        //   user1.txt
        // However, if the user input is:
        //   ..\secret\allsecrets.txt
        // Then an attacker can now see all the secrets.

        // Avoid this:
        using (File.Open(userInput, FileMode.Open))
        {
            // Read a file with the name supplied by user
            // Input through request's query string and display
            // The content to the webpage.
        }
    }
}
```

```vb
Imports System
Imports System.IO

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim userInput As String = Me.Request.Params("UserInput")
        ' Assume the following directory structure:
        '   wwwroot\currentWebDirectory\user1.txt
        '   wwwroot\currentWebDirectory\user2.txt
        '   wwwroot\secret\allsecrets.txt
        ' There is nothing wrong if the user inputs:
        '   user1.txt
        ' However, if the user input is:
        '   ..\secret\allsecrets.txt
        ' Then an attacker can now see all the secrets.

        ' Avoid this:
        Using File.Open(userInput, FileMode.Open)
            ' Read a file with the name supplied by user
            ' Input through request's query string and display
            ' The content to the webpage.
        End Using
    End Sub
End Class
```
