---
title: Instalace systémů testů jednotek od třetích stran
ms.date: 06/07/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 4cf2635cf46b1fa8b395cb8a7cab8769ae6ed6d3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960111"
---
# <a name="install-unit-test-frameworks"></a>Nainstalujte rozhraní pro testování částí

Visual Studio Test Explorer můžete spustit libovolné jednotky rozhraní testování, který byl vyvinut rozhraní adaptér pro Průzkumníka. Instalační program rozhraní Framework nainstalují binární soubory a přidá šablony projektů Visual Studio pro jazyky, které podporuje. Při vytváření projektu se šablonou rozhraní zaregistrován pomocí Průzkumníka testů. Řešení sady Visual Studio může obsahovat projektů testů jednotek, které používají různá rozhraní a, který cílí na různé jazyky. Průzkumník testů provádí s nimi všechny.

[MSTest](getting-started-with-unit-testing.md) je rozhraní pro testování poskytovaný sadou Visual Studio a je ve výchozím nastavení nainstalované s Visual Studio.

## <a name="acquire-frameworks"></a>Získání rozhraní

Můžete stáhnout a nainstalovat rozhraní pro testování jednotky třetí strany, pomocí Správce rozšíření sady Visual Studio nebo z [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Rozhraní můžete také stáhnout z jiných webů, jako je web rozhraní framework.

### <a name="install-from-visual-studio"></a>Instalace ze sady Visual Studio

1. Zvolte **nástroje** ve standardní nabídce a klikněte na tlačítko **rozšíření a aktualizace**.

2. Rozbalte **Online** > **Visual Studio Marketplace** > **nástroje**. Zvolte **testování**.

3. Procházejte seznamem a najít rozhraní framework.

4. Vyberte rozhraní a zvolte **Stáhnout**.

Další informace najdete v části [vyhledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).

### <a name="install-from-the-web"></a>Instalace z webu

Pokud znáte rozhraní, které vás zajímají:

1. Otevřít [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs).

2. Zadejte název rozhraní v **najít** pole.

3. Zvolte v seznamu výsledků a přejděte do rozhraní **Visual Studio Marketplace** stránky pro nástroj.

Můžete procházet seznam architektur společně s další testovací nástroje:

1. Otevřít [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs).

2. V **filtrovat podle kategorie / kolekce**, zvolte **zobrazit všechny**.

3. V **kategorie** seznamu (označené jako **zobrazující**), rozbalte **nástroje** uzlu a pak zvolte **testování**.

4. Výběr v seznamu výsledků a přejděte do architektury **Visual Studio Marketplace** stránky pro nástroj.

## <a name="update-to-the-latest-test-adapters"></a>Aktualizovat na nejnovější adaptéry testu

Aktualizace na nejnovější stabilní testovací adaptér, který má lepší prostředí testování a spuštění zjišťování. Další informace o aktualizacích adaptéry testů xUnit, MSTest a NUnit, najdete v článku [blogu sady Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>Aktualizovat na nejnovější stabilní test adapter verze

1. Otevřete Správce balíčků Nuget pro řešení tak, že přejdete do **nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet pro řešení**.

2. Klikněte na **aktualizace** kartu a vyhledejte xUnit, MSTest nebo NUnit testování adaptéry, které jsou nainstalovány.

3. Vyberte jednotlivé adaptéry testu a pak v rozevírací nabídce vyberte nejnovější stabilní verzi.

4. Zvolte **nainstalovat** tlačítko.

   ![Upgrade adaptéru testu](media/install-adapter-upgrade.png)

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)
