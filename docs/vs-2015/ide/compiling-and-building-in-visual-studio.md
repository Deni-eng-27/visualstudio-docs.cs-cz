---
title: Kompilování a sestavování
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
caps.latest.revision: 30
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d8ec7d6508ec025a2b2005754da03bdd4db38943
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300257"
---
# <a name="compiling-and-building-in-visual-studio"></a>Kompilování a sestavování v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Systém Visual Studio lze použít k vytváření aplikací a k vytváření sestavení a spustitelných programů v pravidelných intervalech v průběhu vývoje. Častým sestavováním kódu lze dříve identifikovat chyby kompilace, jako je nesprávná syntaxe, překlepy v klíčových slovech a neshody typů. Častým sestavováním a spouštěním ladicí verze kódu lze také zjistit a opravit chyby za běhu, jako jsou logické a sémantické chyby.

 Pokud jste projekt nebo řešení plně vyvinuli a dostatečně odladili, lze jeho komponenty zkompilovat do sestavení určeného pro vydání. Ve výchozím nastavení je sestavení pro vydání optimalizováno a navrženo tak, aby bylo menší a rychlejší než ladicí verze. Další informace najdete v tématu [názorný postup: Tvorba aplikace](../ide/walkthrough-building-an-application.md).

## <a name="choosing-a-build-method"></a>Výběr metody sestavení
 Aplikaci lze sestavit pomocí výchozích možností sestavení v integrovaném vývojovém prostředí (IDE), v příkazovém řádku nebo pomocí systému Team Foundation Build. Každá z těchto možností použije nástroj MSBuild jako podkladovou technologii a každý přístup má určité výhody, jak ukazuje následující tabulka.

|Metoda sestavení|Výhody|Další informace|
|------------------|--------------|--------------------------|
|Používání prostředí IDE|– Můžete snadno vytvořit a spouštět sestavení okamžitě.<br />-Lze spustit víceprocesorová sestavení pro projekty jazyka C++ a C#.<br />-Si můžete přizpůsobit některé aspekty systému sestavení.|[Sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)|
|Spuštění příkazového řádku MSBuild|-Projekty lze sestavit bez instalace sady Visual Studio.<br />-Lze spustit víceprocesorová sestavení pro všechny typy projektů.<br />-Si můžete přizpůsobit většinu oblastí systému sestavení.|[MSBuild](../msbuild/msbuild.md)|
|Použití systému Team Foundation Build|-Můžete automatizovat proces sestavení. Lze například sestavit jeden nebo více projektů v noci nebo pokaždé, když je kód vrácen se změnami. Projekty lze také sestavit na sdílených serverech sestavení a nikoli na vašem vývojovém počítači.<br />– Je možné rychle zadat kód, který chcete sestavit, testy, které chcete spustit, a další běžné možnosti.<br />– Můžete upravit pracovní postup sestavení a podle potřeby a vytvořit aktivity sestavení provést hluboce přizpůsobené úkoly.|[Sestavení aplikace](/azure/devops/pipelines/index)|

## <a name="building-from-the-ide"></a>Sestavení v prostředí IDE
 Při vytváření projektu jsou definovány výchozí konfigurace sestavení a konfigurace sestavení řešení je přiřazena k projektu, čímž poskytuje kontext sestavení. Konfigurace řešení definují, jak jsou projekty v řešení sestaveny a nasazeny. Konfigurace projektu představují sadu vlastností projektu, které jsou jedinečné pro platformu a typ sestavení (například Vydaná verze Win32). Tyto výchozí konfigurace lze upravit a lze vytvořit vlastní konfigurace. Další informace najdete v tématu [Úvod do Návrháře projektu](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7) a [NIB jak: Upravte vlastnosti projektu a nastavení konfigurace](https://msdn.microsoft.com/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67).

 V rozhraní IDE lze provádět následující dodatečné úkoly:

- [Změna výstupního adresáře sestavení](../ide/how-to-change-the-build-output-directory.md).

- [Identifikovat projekty, které jsou závislé na výstupu z jiného projektu, aby se sestavily správně](../ide/how-to-create-and-remove-project-dependencies.md).

- [Změnit množství informací o zahrnutých v protokolu sestavení nebo v okně výstupu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md).

- [Skrýt upozornění kompilátoru specifické pro jazyk Visual C#, Visual C++ nebo Visual Basic](../ide/how-to-suppress-compiler-warnings.md).

- [Zadejte vlastní před kompilací a po kompilaci akce sestavení](../ide/specifying-custom-build-events-in-visual-studio.md).

- Zvýšit výkon sestavení pomocí paralelních sestavení Další informace najdete v tématu [sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md) nebo blogový příspěvek [paralelního sestavení ladění jazyka C++](https://blogs.msdn.microsoft.com/msbuild/2010/03/07/tuning-c-build-parallelism-in-vs2010/).

## <a name="see-also"></a>Viz také
 [Návod: Sestavení aplikace](../ide/walkthrough-building-an-application.md) [Principy konfigurace sestavení](../ide/understanding-build-configurations.md) [platformy sestavení Principy](../ide/understanding-build-platforms.md) [vytváření webových projektů (kompilace)](https://msdn.microsoft.com/library/a9cbb88c-8fff-4c67-848b-98fbfd823193) [Postupy: vytváření a odebrání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md)
