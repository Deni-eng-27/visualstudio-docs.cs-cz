---
title: 'Průvodce: Ladění textové šablony přistupující k modelu'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 50190afd6dfbda054ab7c1636bb0f0f89984117a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55004497"
---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>Průvodce: Ladění textové šablony přistupující k modelu
Při úpravě nebo přidat textové šablony řešení jazyka specifického pro doménu, může docházet k chybám při modul transformace šablony zdrojový kód nebo při kompilaci vygenerovaného kódu. Následující návod znázorňuje některé z akcí, které vám pomůžou ladění textové šablony.

> [!NOTE]
>  Další informace o textu šablony, najdete v článku [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md). Další informace o ladění textové šablony najdete v tématu [názorný postup: Ladění textové šablony](debugging-a-t4-text-template.md).

## <a name="creating-a-domain-specific-language-solution"></a>Vytváření řešení jazyka specifického pro doménu
 V tomto postupu vytvoříte řešení jazyka specifického pro doménu, která má následující vlastnosti:

- Jméno: DebuggingTestLanguage

- Šablona řešení: Minimální jazykový

- Přípona souboru: .ddd

- Název společnosti: Společnost Fabrikam

  Další informace o vytváření řešení jazyka specifického pro doménu, najdete v části [jak: Vytváření řešení jazyka specifického pro doménu](../modeling/how-to-create-a-domain-specific-language-solution.md).

## <a name="creating-a-text-template"></a>Vytvoření textové šablony
 Přidejte textové šablony do vašeho řešení.

#### <a name="to-create-a-text-template"></a>Vytvoření textové šablony

1.  Sestavte řešení a začít spouštět v ladicím programu. (Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**a pak na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.) Novou instanci sady Visual Studio otevře ladění projektu.

2.  Přidání textového souboru s názvem `DebugTest.tt` k ladění projektu.

3.  Ujistěte se, že **Custom Tool** vlastnost DebugTest.tt je nastavena na `TextTemplatingFileGenerator`.

## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>Ladění direktivy, které přístup k modelu z textové šablony
 Pro přístup k modelu z příkazy a výrazy v textové šabloně, je třeba nejprve zavolat procesoru vygenerovaných direktiv. Volání procesoru vygenerovaných direktiv zpřístupní třídami v modelu kód textové šablony jako vlastnosti. Další informace najdete v tématu [přístup k modelům z textových šablon](../modeling/accessing-models-from-text-templates.md).

 V následujících postupech který budete ladit nesprávný název směrnice a nesprávná vlastnost název.

#### <a name="to-debug-an-incorrect-directive-name"></a>Chcete-li ladit nesprávný název direktivy

1.  Nahraďte kód v DebugTest.tt následujícím kódem:

    > [!NOTE]
    >  Kód obsahuje chybu. Představujete chyby, aby bylo možné ladit.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na DebugTest.tt a potom klikněte na tlačítko **spustit vlastní nástroj**.

     **Seznam chyb** v okně se zobrazí tato chyba:

     **Procesor s názvem "DebuggingTestLanguageDirectiveProcessor" nepodporuje direktivu s názvem "modelRoot". Transformace se nespustí.**

     V takovém případě direktiv volání obsahuje nesprávný název direktivy. Zadali jste `modelRoot` je název direktivy, ale správný název direktivy `DebuggingTestLanguage`.

3.  Klikněte dvakrát na chybu v **seznam chyb** okna můžete přejít ke kódu.

4.  Chcete-li kód, změňte název direktivy k `DebuggingTestLanguage`.

     Tato změna se zvýrazní.

    ```csharp
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

    ```vb
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

5.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na DebugTest.tt a potom klikněte na tlačítko **spustit vlastní nástroj**.

     Systém nyní transformace textové šablony a generuje odpovídající soubor výstup. Neuvidíte všechny chyby **seznam chyb** okna.

#### <a name="to-debug-an-incorrect-property-name"></a>Chcete-li ladit s názvem nesprávná vlastnost

1.  Nahraďte kód v DebugTest.tt následujícím kódem:

    > [!NOTE]
    >  Kód obsahuje chybu. Představujete chyby, aby bylo možné ladit.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na DebugTest.tt a potom klikněte na tlačítko **spustit vlastní nástroj**.

     **Seznam chyb** okno se zobrazí a zobrazí se jedné z následujících chyb:

     (C#)

     **Kompilování transformace: Microsoft.VisualStudio.TextTemplating\<GUID>. GeneratedTextTransformation' neobsahuje definici pro 'ExampleModel.**

     (Visual Basic)

     **Kompilování transformace: "ExampleModel" není členem "Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation ".**

     V tomto případě kód textové šablony obsahuje název nesprávná vlastnost. Zadali jste `ExampleModel` jako název vlastnosti, ale vlastnost správný název je `LibraryModel`. Můžete najít správné vlastnosti název v poskytuje parametru, jak je znázorněno v následujícím kódu:

    ```
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>
    ```

3.  Klikněte dvakrát na chybu v okně Seznam chyb pro přechod na kód.

4.  Chcete-li kód, změňte vlastnost název na `LibraryModel` v kód textové šablony.

     Změny jsou zvýrazněné.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.LibraryModel #>
    <#
    foreach (ExampleElement element in this.LibraryModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.LibraryModel #>
    <#
    For Each element as ExampleElement in Me.LibraryModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

5.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na DebugTest.tt a potom klikněte na tlačítko **spustit vlastní nástroj**.

     Systém nyní transformace textové šablony a generuje odpovídající soubor výstup. Neuvidíte všechny chyby **seznam chyb** okna.