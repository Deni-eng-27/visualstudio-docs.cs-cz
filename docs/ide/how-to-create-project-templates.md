---
title: Vytváření šablon projektu
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: d0d15d4f3836ca1ccfdc800ad4805ed7691e4454
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990224"
---
# <a name="how-to-create-project-templates"></a>Postupy: Vytváření šablon projektu

V tomto tématu se dozvíte, jak vytvořit šablonu pomocí **Průvodce exportem šablony**, která zabalí vaše šablony v *ZIP* souboru.

## <a name="to-create-a-user-project-template-by-using-the-export-template-wizard"></a>Chcete-li vytvořit šablonu projektu uživatele s použitím Průvodce exportem šablony

1. Vytvoření projektu.

    > [!NOTE]
    > Při pojmenování projektu, který bude sloužit jako zdroj šablony, používejte pouze znaky platný identifikátor. V opačném případě kompilace může dojít k chybám v projektech, které jsou vytvořeny ze šablony. Další informace o platný identifikátor znacích naleznete v tématu [deklarované názvy elementu (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) nebo [identifikátory (C++)](/cpp/cpp/identifiers-cpp). Alternativně můžete použít [parametry šablony](../ide/template-parameters.md) používat "bezpečné" názvy tříd a obory názvů.

2. Upravte projekt, dokud nebude připravený exportovat jako šablonu. Například můžete chtít upravit soubory kódu k označení, kde by měla probíhat náhrada parametru. Zobrazit [jak: Nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).

3. Na **projektu** nabídce zvolte **exportovat šablonu**.

   **Průvodce exportem šablony** otevře.

4. Na **zvolte typ šablony** stránce **šablonu projektu**. Vyberte projekt, který chcete exportovat do šablony a klikněte na tlačítko **Další**.

5. Na **vyberte možnosti šablony** stránky, zadejte název a volitelný popis, ikona a zobrazit jejich náhled obrázku pro šablonu. Tyto položky se zobrazí v **nový projekt** dialogové okno. Zvolte **Dokončit**.

   Projekt se exportuje do *ZIP* soubor a umístí do zadané výstupní umístění a, k importu do sady Visual Studio.

>[!NOTE]
> Najít šablonu v **nový projekt** dialogového okna rozbalte **nainstalováno** a potom rozbalte kategorii, která odpovídá `ProjectType` element v *.vstemplate*souboru. Například *.vstemplate* soubor, který obsahuje `<ProjectType>CSharp</ProjectType>` se zobrazí v části **nainstalováno** > **Visual C#** , ve výchozím nastavení. Šablony můžete uspořádat do podadresáře typu projektu, stačí jim k vytvoření složky v tomto adresáři a uvedení do šablony *ZIP* soubor v ní. Další informace najdete v tématu [jak: Hledání a organizace šablon](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="other-ways-to-create-project-templates"></a>Další způsoby vytváření šablon projektu

Šablony projektů můžete vytvořit ručně tak, že shromažďování souborů, které tvoří projektu do složky a pak vytvořit *.vstemplate* soubor XML s příslušná metadata. Další informace najdete v tématu [jak: Ruční vytvoření webových šablon](../ide/how-to-manually-create-web-templates.md).

Pokud máte nainstalované Visual Studio SDK, můžete zabalit dokončená šablona v souboru VSIX pro nasazení pomocí **projekt VSIX** šablony. Další informace najdete v tématu [Začínáme s šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Viz také:

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: Tvorba šablon položek](../ide/how-to-create-item-templates.md)
- [Začínáme s šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)