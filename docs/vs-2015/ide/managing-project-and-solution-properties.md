---
title: Správa vlastností projektů a řešení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: d727efc0-1096-4ede-84b6-31a65da22ac0
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dc27bd0cb93ab142d2a82758c72b27d14032d04e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674982"
---
# <a name="managing-project-and-solution-properties"></a>Správa vlastností projektů a řešení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Projekty mají vlastnosti, které řídí mnoho aspektů kompilace, ladění, testování a nasazení. Některé vlastnosti jsou společné mezi všechny typy projektů a některé jsou jedinečné pro konkrétní jazyky a platformy. Přístup vlastnosti projektu tak, že kliknete pravým tlačítkem na uzel projektu v Průzkumníku řešení a zvolíte vlastnosti nebo zadáním vlastnosti do **rychlé spuštění** vyhledávacího pole v řádku nabídek.  
  
 ![Místní nabídky projekt](../ide/media/vs2015-proj-prop-menu.gif "vs2015_proj_prop_menu")  
  
 Projekty .NET také mít vlastnosti uzel ve stromu projektu, samotného.  
  
 ![Vlastnosti uzlu stromové struktury Průzkumníka řešení](../ide/media/vs2015-props-se.png "VS2015_Props_SE")  
  
> [!TIP]
> Řešení mít několik vlastností a tak projektové položky. Tyto vlastnosti jsou přístupné z [okno vlastností](../ide/reference/properties-window.md), nikoli **Návrháře projektu**.  
  
## <a name="project-properties"></a>Vlastnosti projektu  
 Vlastnosti projektu jsou uspořádány do skupin a každá skupina má svou vlastní stránku vlastností a stránky můžou být různé pro různé jazyky a typy projektů.  
  
### <a name="c-and-visual-basic-projects"></a>Projekty jazyka C# a Visual Basic  
 V projektech C# a Visual Basic, jsou přístupné vlastnosti **Návrháře projektu**. Následující obrázek znázorňuje stránky vlastností sestavení pro projekt WPF v jazyce C#:  
  
 ![Visual Studio Project Designer](../ide/media/vs2015-proppage-build.png "VS2015_PropPage_Build")  
  
 Informace o jednotlivých stránek vlastností v Návrháři projektu naleznete v tématu [referenční dokumentace k vlastnostem projektu](../ide/reference/project-properties-reference.md).  
  
### <a name="c-and-javascript-projects"></a>Projekty C++ a JavaScript  
 Projekty C++ a JavaScript mít různé uživatelské rozhraní pro správu vlastností projektu. Tento obrázek znázorňuje stránky vlastností projektu jazyka C++ (stránky JavaScript jsou podobné):  
  
 ![Visual C&#43;&#43; project properties](../ide/media/vs2015-projprops-cpp.png "VS2015_ProjProps_cpp")  
  
 Informace o vlastnostech projektů C++, naleznete v tématu [práce s vlastnostmi projektu](https://msdn.microsoft.com/library/9b0d6f8b-7d4e-4e61-aa75-7d14944816cd). Další informace o vlastnostech jazyka JavaScript naleznete v tématu [stránky vlastností, JavaScript](../ide/reference/property-pages-javascript.md).  
  
## <a name="solution-properties"></a>Vlastnosti řešení  
 Přístup k vlastnostem na řešení, klikněte pravým tlačítkem myši na uzel řešení v **Průzkumníka řešení** a zvolte **vlastnosti**. V dialogovém okně můžete nastavit projekt konfigurace pro ladění nebo vydání verze sestavení, zvolte projekty, které (s) by měl být projekt po spuštění v případě stisknutí F5 a nastavte možnosti analýzy kódu.  
  
## <a name="see-also"></a>Viz také  
 [Řešení a projekty v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)
