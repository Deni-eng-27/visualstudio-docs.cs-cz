---
title: 'Návrhář postupu provádění - postupy: Přidání nové položky do projektu pracovního postupu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0aa2be7fd8ecccbd8de0aa54c2693dd6b02c7e10
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Postupy: Přidání nové položky do projektu pracovního postupu

Po vytvoření projektu workflow, můžete přidat do projektu aktivity pracovního postupu, Designer a další známé položky Visual Studio.

Následující tabulka uvádí položky Windows Workflow Foundation (WF), které můžete přidat do projektu pracovního postupu.

|Název|Popis|
|----------|-----------------|
|Aktivita|Aktivity k musí se skládat z jiné aktivity. Výběrem této položky přidá ke stejnému souboru XAML do projektu, jak lze získat při výběru **knihovna aktivit** šablonu pro nový projekt. Další informace o na tomto postupu najdete v tématu [postupy: vytvoření knihovna aktivit](../workflow-designer/how-to-create-an-activity-library.md).|
|Návrhář aktivity|Návrhář přizpůsobit prostředí návrhu aktivity. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **knihovny návrháře aktivit** šablonu pro nový projekt. Další informace o na tomto postupu najdete v tématu [postupy: vytvoření knihovny návrháře aktivit](../workflow-designer/how-to-create-an-activity-designer-library.md).|
|Kód aktivity|Aktivita, jejíž logiky provádění napsané v kódu. Soubor zdrojového kódu se pomocí přepsání <xref:System.Activities.CodeActivity.Execute%2A> metoda byl již vygenerován za vás.|
|Pracovní postup služby WCF|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] služby vytvořené pomocí aktivity pracovního postupu. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **aplikace služby pracovního postupu WCF** šablonu pro nový projekt. Další informace o tomto postupu najdete v tématu [postupy: vytvoření aplikace služby pracovního postupu WCF](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>Chcete-li přidat novou položku do projektu pracovního postupu

1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku...** .

     **Přidat novou položku** otevře se dialogové okno.

2.  V **nainstalovaných šablonách** podokně, vyberte **pracovního postupu** skupiny.

3.  Vyberte jeden ze čtyř položky. V předchozí tabulce jsou uvedeny možnosti, které jsou k dispozici.

4.  Zadejte vhodný název pro položku v **název** pole v dolní části dialogových oken.

5.  Klikněte na tlačítko **přidat** přidat položku do aktuálního projektu pracovního postupu.

## <a name="see-also"></a>Viz také

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)