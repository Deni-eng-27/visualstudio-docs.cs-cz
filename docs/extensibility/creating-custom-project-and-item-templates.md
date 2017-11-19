---
title: "Vytváření vlastních projektů a šablon položek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e99505c0d3c4ee59f6e07a5b38d5d95533ab879f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-custom-project-and-item-templates"></a>Vytváření vlastních projektů a šablon položek
Visual Studio SDK obsahuje šablony projektů, které vytvořit vlastní šablonu projektu a šablonu vlastní položky. Tyto šablony zahrnují některé běžné nahrazení parametru a sestavení jako soubory zip. Se nenasadí automaticky a nejsou k dispozici v experimentální instanci. Je nutné zkopírovat souboru zip souborů k umístění  
  
 Šablony pro vytvoření šablony umožňují zahrnout šablony větší rozšíření. To umožňuje implementovat řízení verze na zdrojové soubory a vytvořit skupinu šablony projektů do jednoho balíčku VSIX.  
  
 Pro scénáře vytváření základní šablon, měli byste použít **exportovat šablonu** průvodce, který výstupy pro komprimovaný soubor. Další informace o vytvoření základní šablony najdete v tématu [vytváření projektů a šablon položek](../ide/creating-project-and-item-templates.md).  
  
 Od verze Visual Studio 2017, hledání vlastních projektů a šablon položek už se provede. Místo toho rozšíření, musíte zadat soubory manifestu šablony, které popisují umístění instalace služby tyto šablony. Visual Studio 2017 můžete použít k aktualizaci VSIX rozšíření. Pokud nasadíte rozšíření pomocí souboru MSI, je nutné ručně Generovat soubory manifestu šablony. Další informace najdete v tématu [upgrade vlastních šablon projektů a položek pro Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schéma manifestu šablony je popsána v [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).  
  
## <a name="creating-a-project-template"></a>Vytvoření šablony projektu  
  
1.  Vytvoření projektu šablona projektu. Můžete najít v šabloně projektů **nový projekt** dialogové okno, v jazyce Visual Basic a Visual C# **rozšiřitelnost** složky.  
  
     Šablona generuje soubor třídy, ikonu, .vstemplate souboru, soubor upravovat projektu s názvem ProjectTemplate.vbproj nebo ProjectTemplate.csproj a některé soubory, které jsou obvykle generují jiné typy projektů, takový resources.resx soubor, AssemblyInfo soubor a soubor .settings. Každý kód soubor obsahuje běžné nahrazení parametru, kde je to vhodné.  
  
2.  Přidání a odebrání položek z projektu podle potřeby pro váš projekt. Neodebírejte soubor upravovat projektu, soubor AssemblyInfo nebo soubor .vstemplate.  
  
3.  Aktualizujte soubor .vstemplate tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) element musí obsahovat [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) element pro každý soubor má být zahrnut v šabloně.  
  
4.  Upravit soubory s kódem a další obsah zobrazující se uživatelům a přidejte náhrady odpovídající parametr.  
  
5.  Upravte generovaného obsahu podle potřeby.  
  
6.  Sestavte projekt.  
  
     Visual Studio vytvoří soubor .zip, který obsahuje šablony. Není nasazená, a není k dispozici v experimentální instanci.  
  
## <a name="creating-an-item-template"></a>Vytvoření šablony položky  
  
1.  Vytvoření projektu šablony položky.  
  
     Šablona generuje soubor třídy, ikonu, soubor .vstemplate a soubor AssemblyInfo. Třída soubor obsahuje některé běžné nahrazení parametru.  
  
2.  Přidání a odebrání položek z projektu podle potřeby pro váš projekt.  
  
3.  Aktualizujte soubor .vstemplate tak, aby odrážela všechny přidání a odstranění. [Projektu](../extensibility/project-element-visual-studio-templates.md) element musí obsahovat [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) element pro každý soubor má být zahrnut v šabloně.  
  
4.  Upravit soubory s kódem a další obsah zobrazující se uživatelům a přidejte náhrady odpovídající parametr.  
  
5.  Upravte generovaného obsahu podle potřeby.  
  
6.  Sestavte projekt.  
  
     Visual Studio vytvoří komprimovaný soubor, který obsahuje šablony. Není nasazená, a není k dispozici v experimentální instanci.  
  
## <a name="deployment"></a>Nasazení  
  
#### <a name="to-deploy-the-project-or-item-template"></a>Pokud chcete nasadit šablonu projektu nebo položky  
  
1.  Vytvoření projektu VSIX. Další informace najdete v tématu [šablona projektu VSIX](../extensibility/vsix-project-template.md).  
  
2.  Nastavte VSIX projekt jako spouštěný projekt. V **Průzkumníku řešení**, vyberte uzel projektu VSIX, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.  
  
3.  Nastavte projekt šablony projektu jako prostředek VSIX projektu. Otevřete soubor .vsixmanifest. Přejděte na **prostředky** a klikněte na **nový**.  
  
    1.  Nastavte **typ** do **Microsoft.VisualStudio.ProjectTemplate** nebo **Microsoft.VisualStudio.ItemTemplate**.  
  
    2.  Pro zdroj, vyberte **na projekt v aktuálním řešení** možnost a potom vyberte projekt, který obsahuje šablony.  
  
4.  Sestavte řešení a stiskněte klávesu F5. Zobrazí se experimentální instanci.  
  
5.  Pro projekt šablony projektu, měli byste vidět uvedené v projektu šablony **nový projekt** dialogové okno (**souboru / New / Project**) v jazyce Visual C# nebo Visual Basic uzlu. Pro projekt šablony položky, měli byste vidět vaší šablony položky, které jsou uvedené v dialogovém okně Přidat novou položku (v **Průzkumníku řešení**, vyberte uzel projektu a klikněte na **přidat / nová položka**).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace šablony sady Visual Studio](../ide/visual-studio-template-reference.md)