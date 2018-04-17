---
title: Cílová verze rozhraní .NET Framework v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/06/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 73cec2f27bfc2e29b9b9faa34c9c24ca2273210e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Postupy: cílení na verzi rozhraní .NET Framework

Tento dokument popisuje, jak cílení na verzi rozhraní .NET Framework, když vytvoříte projekt a jak změnit cílovou verzi v existující jazyka Visual Basic, C# nebo Visual F # projektu.

> [!IMPORTANT]
> Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="to-target-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu

Při vytváření projektu, k dispozici verze rozhraní .NET Framework závisí na verzí instalovaných a vybrané šablony **nový projekt** dialogové okno.

1. Na řádku nabídek zvolte **soubor** > **nový** > **projektu...** .

1. V seznamu nainstalovaných šablon vyberte typ projekt, který chcete vytvořit a zadejte název projektu.

1. Z **Framework** rozevíracím seznamu v dolní části **nový projekt** dialogovém okně vyberte verzi rozhraní .NET Framework, pokud chcete k cíli.

    V seznamu rozhraní jsou uvedeny pouze verze, které platí pro šablonu, kterou jste zvolili. Některé typy projektů, jako je například .NET Core, nevyžadují, aby rozhraní .NET Framework. V takových případech **Framework** rozevíracího seznamu skryt.

    ![Framework rozevíracího seznamu v dialogovém okně Nový projekt](media/vside-newproject-framework.png)

1. Vyberte **OK** tlačítko.

## <a name="to-change-the-targeted-version"></a>Změna cílené verze

Pomocí tohoto postupu můžete změnit cílové verze rozhraní .NET Framework v projektu jazyka Visual Basic, C# nebo Visual F #.

Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

1. V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete změnit a potom vyberte **vlastnosti**.

    ![Visual Studio Solution Explorer Properties](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")

1. V levém sloupci okna vlastností, vyberte **aplikace** kartě.

    ![Visual Studio aplikace vlastnosti aplikace karta](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")

    > [!NOTE]
    > Po vytvoření aplikace pro UPW, nelze změnit cílovou verzi systému Windows nebo rozhraní .NET Framework.

1. V **cílové rozhraní** vyberte verzi, která chcete.

1. V dialogovém okně ověření zvolte **Ano** tlačítko.

    Projekt se uvolní. Až se znovu načte, bude cílit na verzi rozhraní .NET Framework, kterou jste vybrali.

    > [!NOTE]
    > Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET Framework, než na kterou cílíte, mohou se při kompilaci či spuštění kódu zobrazit chybové zprávy. Chcete-li tyto chyby vyřešit, je třeba upravit odkazy. V tématu [řešení potíží s cílením rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Viz také

[Přehled cílení na více verzí sady Visual Studio](../ide/visual-studio-multi-targeting-overview.md)  
[Řešení potíží s cílením na rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)  
[Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)  
[Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Postupy: Změna cílové architektury a sady nástrojů (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)