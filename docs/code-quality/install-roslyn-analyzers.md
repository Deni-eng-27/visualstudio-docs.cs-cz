---
title: Nainstalovat analyzátory třetích stran
ms.date: 08/27/2020
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 9da78f4c8e76f4e5b79f4cbdb0739d34fc465330
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "89091448"
---
# <a name="install-third-party-analyzers"></a>Instalace analyzátorů jiných výrobců

Sada Visual Studio obsahuje základní sadu analyzátorů .NET Compiler Platform (*Roslyn*). Tyto analyzátory jsou vždycky zapnuté. Můžete nainstalovat další analyzátory buď jako balíčky NuGet, nebo jako rozšíření sady Visual Studio v souborech *VSIX* .

## <a name="to-install-nuget-analyzer-packages"></a>Instalace balíčků analyzátoru NuGet

1. Najděte balíček analyzátoru, který chcete nainstalovat na www.nuget.org.

   Například můžete chtít nainstalovat [StyleCop. analyzers](https://www.nuget.org/packages/stylecop.analyzers/) pro hledání problémů se stylem v základu kódu.

2. Nainstalujte balíček v aplikaci Visual Studio pomocí [konzoly Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) nebo [uživatelského rozhraní Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > Stránka www.nuget.org pro každý balíček analyzátoru zobrazuje příkaz pro vložení do **konzoly Správce balíčků**. Je k dispozici i praktické tlačítko ke zkopírování textu do schránky.

   Sestavení analyzátoru jsou nainstalována a zobrazí se v **Průzkumník řešení** v části **References**  >  **analyzátory**odkazů.

## <a name="to-install-vsix-analyzers"></a>Instalace analyzátorů VSIX

::: moniker range="vs-2017"

1. V aplikaci Visual Studio vyberte **Tools** > **rozšíření nástrojů a aktualizace**.

   Otevře se dialogové okno **rozšíření a aktualizace** .

   > [!NOTE]
   > Alternativně můžete najít rozšíření analyzátoru a stáhnout ho přímo z [Visual Studio Marketplace](https://marketplace.visualstudio.com).

::: moniker-end

::: moniker range=">=vs-2019"

1. V aplikaci Visual Studio vyberte **rozšíření** > **Spravovat rozšíření**.

   Otevře se dialogové okno **Spravovat rozšíření** .

   > [!NOTE]
   > Alternativně můžete najít rozšíření analyzátoru a stáhnout ho přímo z [Visual Studio Marketplace](https://marketplace.visualstudio.com).

::: moniker-end

2. V levém podokně rozbalte položku **online** a vyberte možnost **Visual Studio Marketplace**.

3. Do vyhledávacího pole zadejte název rozšíření analyzátoru, které chcete nainstalovat. Například můžete chtít [nainstalovat analyzátory nástroje Microsoft FxCop](install-fxcop-analyzers.md#vsix) , abyste mohli kontrolovat kód pro problémy se zabezpečením a výkonem mimo jiné.

4. Vyberte **Stáhnout**.

   Rozšíření se stáhne.

5. Kliknutím na **tlačítko OK** zavřete dialogové okno a poté zavřete všechny instance aplikace Visual Studio a spusťte **instalační program VSIX**.

   Otevře se dialogové okno **instalátor VSIX** .

   ![Instalační program VSIX pro analýzu kódu Microsoft](media/vsix-installer-code-analysis.png)

6. Kliknutím na tlačítko **změnit** spusťte instalaci.

7. Po jedné nebo dvou minutách se instalace dokončí. Vyberte **Zavřít**.

8. Znovu otevřete Visual Studio.

::: moniker range="vs-2017"

Chcete-li ověřit, zda je rozšíření nainstalováno, vyberte **Tools**možnost  >  **rozšíření a aktualizace**nástroje. V dialogovém okně **rozšíření a aktualizace** vyberte **nainstalovanou** kategorii na levé straně a potom vyhledejte rozšíření podle názvu.

::: moniker-end

::: moniker range=">=vs-2019"

Chcete-li ověřit, zda je rozšíření nainstalováno, vyberte **rozšíření**  >  **Spravovat rozšíření**. V dialogovém okně **Spravovat rozšíření** vyberte v levé části kategorii **nainstalováno** a pak vyhledejte rozšíření podle názvu.

::: moniker-end

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Použití analyzátorů kódu v aplikaci Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Viz také

- [Přehled analyzátorů kódu v aplikaci Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Instalace analyzátorů FxCop](../code-quality/install-fxcop-analyzers.md)
