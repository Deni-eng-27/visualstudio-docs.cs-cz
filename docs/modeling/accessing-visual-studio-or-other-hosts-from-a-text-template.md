---
title: Přístup k prostředí Visual Studio nebo k jiným hostitelům z textové šablony
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26845b3878a89ea52a3f77f9a0a8d23363877edd
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870679"
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>Přístup k aplikaci Visual Studio nebo k jiným hostitelům z textové šablony

V textové šabloně můžete použít metody a vlastnosti, které jsou vystavené na hostitele, který provede šablony. Visual Studio je příkladem hostitele.

> [!NOTE]
> V pravidelných textových šablon, ale ne v můžete použít hostitele metody a vlastnosti *předzpracovaná* textových šablon.

## <a name="obtain-access-to-the-host"></a>Získat přístup k hostiteli

Chcete-li získat přístup k hostiteli, nastavte `hostspecific="true"` v `template` směrnice. Nyní můžete použít `this.Host`, který má typ [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110)). Typ [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110)) má členy, které můžete použít k překladu názvů souborů a chyb protokolu, například.

### <a name="resolve-file-names"></a>Přeložit názvy souborů

Chcete-li najít úplnou cestu k souboru relativně vzhledem k textu šablony, použijte `this.Host.ResolvePath()`.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>Zobrazení chybových zpráv

V tomto příkladu se zaprotokoluje při transformaci šablony. Pokud je hostitel Visual Studio, chyby se přidají do **seznam chyb**.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>Pomocí sady Visual Studio rozhraní API

Pokud se spuštění textové šablony v sadě Visual Studio, můžete použít `this.Host` pro přístup ke službám poskytuje Visual Studio a všechny balíčky a rozšíření, která jsou načtena.

Nastavit hostspecific = "true" a přetypovat `this.Host` k <xref:System.IServiceProvider>.

V tomto příkladu získává rozhraní API sady Visual Studio, <xref:EnvDTE.DTE>, jako služba:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>Pomocí šablony dědičnosti hostSpecific

Zadejte `hostspecific="trueFromBase"` Pokud používáte také `inherits` atribut, a pokud je zděděn ze šablony, která určuje `hostspecific="true"`. Pokud to neuděláte, může se zobrazit upozornění, které kompilátor vlastnost `Host` byla deklarována dvakrát.