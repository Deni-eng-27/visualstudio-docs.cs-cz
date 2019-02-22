---
title: 'Postupy: Přidejte soubor prostředků | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2fd519b396f5120b7b0acca8d2e6144e363ab1f0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633054"
---
# <a name="how-to-add-a-resource-file"></a>Postupy: Přidejte soubor prostředků
  Příkazy pro přidání souborů prostředků je v místní nabídce řešení uzlů a uzly funkce v Průzkumníku řešení. Další informace najdete v tématu [řešení služby SharePoint lokalizace](../sharepoint/localizing-sharepoint-solutions.md).

### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Chcete-li přidat globální soubor prostředků pro řešení služby SharePoint

1. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení služby SharePoint.

2. V **Průzkumníka řešení**, zvolte uzel projektu služby SharePoint a pak na panelu nabídek zvolte **projektu** > **přidat novou položku**.

3. V **přidat novou položku** dialogového okna zvolte **globální soubor prostředků** šablony a klikněte na tlačítko **přidat** tlačítko.

   > [!NOTE]
   >  Globální soubor prostředků šablony položky projektu se zobrazí, jenom když vyberete položku Sharepointového projektu.

4. V **přidat prostředek** dialogového okna zvolte jazykovou verzi pro soubor prostředků, jako je například angličtina (Spojené státy).

    Tento krok přidává globální soubor prostředků do vašeho řešení ve formátu Resource_x_**.** <em>jazykovou verzi</em><strong>.</strong> resx, jako jsou například *Resource1.en US.resx*.

5. Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.

### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Přidání souborů prostředků funkce do funkce služby SharePoint

1.  Pokud řešení služby SharePoint již není otevřen v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení.

2.  V **Průzkumníka řešení**, otevřete místní nabídku pro název funkce v rámci **funkce** uzel a klikněte na tlačítko **přidat prostředek funkce**.

     Tento krok přidá soubor prostředků pro funkce ve formátu, _ResourceFileName_**.** _jazykovou verzi_**RESX**, jako jsou například *Feature1.en US.resx*.

3.  Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.

## <a name="see-also"></a>Viz také:
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
