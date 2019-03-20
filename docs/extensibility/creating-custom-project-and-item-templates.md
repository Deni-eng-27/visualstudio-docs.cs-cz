---
title: Vytváření vlastních projektů a šablon položek | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 01af6001bd116fd2b523668eddbdc68d2dd5beab
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194467"
---
# <a name="create-custom-project-and-item-templates"></a>Vytváření vlastních šablon projektů a položek

Visual Studio SDK zahrnuje šablony projektu, které vytvořit vlastní šablonu projektu a šablonu vlastní položky. Tyto šablony zahrnují některých běžných náhrad parametrů a sestavení jako soubory zip. Nejsou nasazeni automaticky a nejsou k dispozici v experimentální instanci aplikace. Musíte zkopírovat soubor generovaný zip do adresáře šablon uživatele.

Vytvoření šablony šablony umožňují zahrnout šablony do větších rozšíření. To vám umožní implementovat správy verzí na zdrojové soubory a vytvořit skupinu šablony projektů do jednoho balíčku VSIX.

Můžete také nakonfigurovat šablonu k instalaci balíčků NuGet. Další informace najdete v tématu [balíčky NuGet v sadě Visual Studio šablony](/nuget/visual-studio-extensibility/visual-studio-templates).

Pro scénáře vytvoření základní šablony, byste měli použít **exportovat šablonu** průvodce, který uloží do komprimovaného souboru. Další informace o vytvoření základní šablony najdete v tématu [vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md).

> [!NOTE]
> Spouští se v sadě Visual Studio 2017, vyhledávání vlastních projektů a šablon položek už se provede. Rozšíření místo toho musíte zadat soubory manifestu šablon, které popisují umístění instalace služby tyto šablony. Visual Studio 2017 můžete použít k aktualizaci rozšíření VSIX. Pokud provádíte nasazení vašeho rozšíření pomocí MSI, musíte soubory manifestu šablony vygenerovat ručně. Další informace najdete v tématu [upgrade vlastních šablon projektů a položek pro Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schéma manifestu šablony je popsána v [odkaz na schéma manifestu šablon sady Visual Studio](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="create-a-project-template"></a>Vytvoření šablony projektu

1. Vytvořte projekt šablony projektu. Můžete najít šablonu projektu v **nový projekt** dialogové okno hledání "Šablona projektu" a výběrem buď C# nebo verze jazyka Visual Basic.

     Tato šablona vygeneruje soubor třídy, ikona *.vstemplate* souboru, soubor upravovat projektu s názvem *ProjectTemplate.vbproj* nebo *ProjectTemplate.csproj*a některé soubory, které jsou obvykle generovány jinými typy projektů takové *resources.resx* souboru *AssemblyInfo* souboru a *.settings* souboru. Každý soubor kódu obsahuje běžné náhrad parametrů, kde je to vhodné.

2. Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt. Neodebírejte soubor upravovat projektu *AssemblyInfo* souboru, nebo *.vstemplate* souboru.

3. Aktualizace *.vstemplate* souboru tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.

4. Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.

5. Upravte vygenerovaný obsah podle potřeby.

6. Sestavte projekt.

     Visual Studio vytvoří *ZIP* soubor, který obsahuje šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.

## <a name="create-an-item-template"></a>Vytvořit šablonu položky

1. Vytvoření šablony položky projektu.

     Tato šablona vygeneruje soubor třídy, ikona *.vstemplate* souboru a *AssemblyInfo* souboru. Soubor třídy obsahuje některé běžné náhrad parametrů.

2. Přidání a odebrání položek z projektu, jak je vyžadováno pro váš projekt.

3. Aktualizace *.vstemplate* souboru tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) musí obsahovat element [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) – element pro každý soubor mají být zahrnuty v šabloně.

4. Upravit soubory kódu a další obsah přístupných a přidejte odpovídající parametr nahrazení.

5. Upravte vygenerovaný obsah podle potřeby.

6. Sestavte projekt.

     Visual Studio vytvoří komprimovaný soubor, který obsahuje šablonu. Není nasazená, a není k dispozici v experimentální instanci aplikace.

## <a name="deployment"></a>Nasazení

### <a name="to-deploy-the-project-or-item-template"></a>Pokud chcete nasadit šablonu projektu nebo položky

1. Vytvořte projekt VSIX. Další informace najdete v tématu [šablonou projektu VSIX](../extensibility/vsix-project-template.md).

2. Nastavte projekt VSIX jako projekt po spuštění. V **Průzkumníka řešení**, vyberte uzel projektu VSIX, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.

3. Nastavte projekt šablony projektu jako prostředek projektu VSIX. Otevřít *.vsixmanifest* souboru. Přejděte **prostředky** kartě a klikněte na tlačítko **nový**.

    1. Nastavte **typ** pole **Microsoft.VisualStudio.ProjectTemplate** nebo **Microsoft.VisualStudio.ItemTemplate**.

    2. Pro zdroj, vyberte **projekt v aktuálním řešení** možnost a potom vyberte projekt, který obsahuje šablonu.

4. Sestavení řešení a stiskněte klávesu **F5**. Zobrazí se experimentální instance.

5. Pro projekt šablony projektu, byste měli vidět uvedené v projektu šablony **nový projekt** dialogového okna (**souboru** > **nový**  >  **Projektu**), Visual C# nebo Visual Basic uzlu. Pro projekt šablony položky, měli byste vidět položku šablony uvedené v **přidat novou položku** dialogového okna. Chcete-li zobrazit **přidat novou položku** dialogového okna, z **Průzkumníka řešení**, vyberte uzel projektu a klikněte na tlačítko **přidat** > **nová položka**).

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace šablony Visual Studio](../ide/creating-project-and-item-templates.md)
- [Balíčky NuGet ve šablony sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)
