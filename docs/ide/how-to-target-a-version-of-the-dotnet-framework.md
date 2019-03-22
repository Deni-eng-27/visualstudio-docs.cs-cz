---
title: Cílení na určitou verzi rozhraní .NET Framework
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba8bdcade321c3660e89ab6b7cf6e0b79471b393
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58355389"
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Postupy: Cílení na verzi rozhraní .NET Framework

Tento článek popisuje, jak cílení na určitou verzi rozhraní .NET Framework při vytváření projektu. Také popisuje, jak změnit cílenou verzi v jazyce Visual Basic se existující C#, nebo F# projektu.

> [!IMPORTANT]
> Informace o tom, jak změnit cílovou verzi pro projekty C++, naleznete v tématu [jak: Upravit na cílové rozhraní framework a sadu nástrojů platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="target-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu

Při vytváření projektu k dispozici verze rozhraní .NET Framework závisí na jaké verze jsou nainstalovány a v šabloně zvoleného projektu.

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

1. Vyberte šablonu pro typ projektu, který chcete vytvořit. Zadejte název projektu.

1. Z **Framework** rozevírací seznam v dolní části dialogového okna zvolte verzi rozhraní .NET Framework, který má váš projekt zaměřit.

   Tento seznam rozhraní obsahuje pouze verze, které se vztahují na šablonu, kterou jste zvolili. Některé typy projektů, jako je .NET Core, nevyžadují, aby rozhraní .NET Framework. V takových případech **Framework** rozevíracího seznamu je skrytá.

   ::: moniker range="vs-2017"

   ![Rozhraní Framework rozevírací seznam v dialogovém okně Nový projekt](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Selektor Framework v VS 2019](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. Pokračujte [vytvořit projekt](create-new-project.md).

## <a name="change-the-targeted-version"></a>Změnit cílovou verzi

Můžete změnit cílovou verzi rozhraní .NET Framework v jazyce Visual Basic C#, nebo F# projekt pomocí tohoto postupu.

1. V **Průzkumníka řešení**, otevřete místní nabídku pro projekt, který chcete změnit a klikněte na tlačítko **vlastnosti**.

    ![Vlastnosti Průzkumníku řešení sady Visual Studio](../ide/media/vs_slnexplorer_properties.png)

1. V levém sloupci **vlastnosti** okna, vyberte **aplikace** kartu.

    ![Visual Studio aplikaci vlastnosti karty](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > Po vytvoření aplikace pro UPW, nelze změnit cílenou verzi systému Windows nebo .NET Framework.

1. V **Cílová architektura** , zvolte verzi, která chcete.

1. V dialogovém okně ověřování, který se zobrazí, zvolte **Ano** tlačítko.

    Projekt se uvolní. Až se znovu načte, bude cílit na verzi rozhraní .NET Framework, kterou jste vybrali.

    > [!NOTE]
    > Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET Framework, než na kterou cílíte, mohou se při kompilaci či spuštění kódu zobrazit chybové zprávy. Chcete-li tyto chyby vyřešit, je třeba upravit odkazy. Zobrazit [rozhraní .NET Framework řešení potíží s cílením](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Viz také:

- [Přehled možností cílení na více Visual Studio](../ide/visual-studio-multi-targeting-overview.md)
- [Řešení potíží s cílením na rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)