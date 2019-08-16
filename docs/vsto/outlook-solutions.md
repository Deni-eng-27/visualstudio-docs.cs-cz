---
title: řešení pro aplikaci Outlook
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Outlook
- Office projects [Office development in Visual Studio], Outlook
- Office solutions [Office development in Visual Studio], Outlook
- templates [Office development in Visual Studio], Outlook
- projects [Office development in Visual Studio], Outlook
- Outlook [Office development in Visual Studio]
- e-mail [Office development in Visual Studio], Outlook solutions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3b27f874766853fb5239c96ec178233935484d1b
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551483"
---
# <a name="outlook-solutions"></a>řešení pro aplikaci Outlook
  Visual Studio poskytuje šablony projektů, pomocí kterých můžete vytvářet doplňky VSTO pro systém Microsoft Office Outlook. Doplňky VSTO můžete použít k automatizaci Outlooku, rozšiřování funkcí Outlooku nebo k přizpůsobení uživatelského rozhraní Outlooku (UI). Další informace o doplňcích VSTO najdete v tématu [architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md).

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="create-an-outlook-vsto-add-in-project"></a>Vytvoření projektu doplňku VSTO pro Outlook
 Vytváření projektů aplikace Outlook pomocí šablony projektu doplňku pro **Outlook** v dialogovém okně **Nový projekt** . Tato šablona obsahuje požadované odkazy na sestavení a soubory projektu.

 Další informace o tom, jak vytvořit projekt doplňku VSTO, najdete v tématu [How to: Vytváření projektů Office v sadě Visual](../vsto/how-to-create-office-projects-in-visual-studio.md)Studio. Další informace o šablonách projektů naleznete v tématu [Přehled šablon projektů Office](../vsto/office-project-templates-overview.md).

## <a name="outlook-vsto-add-in-programming-model"></a>Programovací model doplňku aplikace Outlook VSTO
 Když vytvoříte projekt doplňku VSTO pro Outlook, Visual Studio vygeneruje třídu, která je volána `ThisAddIn`, což je základem vašeho řešení. Tato třída poskytuje výchozí bod pro psaní kódu a také zpřístupňuje objektový model aplikace Outlook pro doplněk VSTO.

 Další informace o `ThisAddIn` třídě a dalších funkcích, které můžete použít v doplňku VSTO, najdete v tématu Programová doplňky [VSTO](../vsto/programming-vsto-add-ins.md).

## <a name="automate-outlook-by-using-the-outlook-object-model"></a>Automatizace Outlooku pomocí objektového modelu aplikace Outlook
 Objektový model aplikace Outlook zpřístupňuje mnoho typů, které lze použít k automatizaci aplikace Outlook. Tyto typy umožňují psát kód pro provádění běžných úloh:

- Programové vytváření a odesílání e-mailových zpráv.

- Odeslat nové žádosti o schůzku.

- Hledat položky ve složkách aplikace Outlook.

  Další informace najdete v tématu [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md).

## <a name="customize-the-user-interface-of-an-outlook-application"></a>Přizpůsobení uživatelského rozhraní aplikace Outlook

|Úloha|Další informace|
|----------|--------------------------|
|Přidejte vlastní karty na pás karet nástroje Outlook Inspector.|[Přehled pásu karet](../vsto/ribbon-overview.md)|
|Přidejte vlastní skupiny do předdefinované karty v okně pro kontrolu aplikace Outlook.|[Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)|
|Přidání vlastního podokna úloh, které se zobrazí v nástroji Outlook Inspector|[Vlastní podokna úloh](../vsto/custom-task-panes.md).|
|Přidejte oblast formuláře, která rozšiřuje nebo nahradí stávající formuláře aplikace Outlook.|[Vytvoření oblastí formuláře aplikace Outlook](../vsto/creating-outlook-form-regions.md)|

 Další informace o přizpůsobení uživatelského rozhraní aplikace Outlook a dalších systém Microsoft Officech aplikací najdete v tématu [přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)|Poskytuje přehled o objektech, které jsou k dispozici v objektovém modelu aplikace Outlook.|
|[Vytvoření oblastí formuláře aplikace Outlook](../vsto/creating-outlook-form-regions.md)|Vysvětluje nástroje poskytované aplikací Visual Studio, které usnadňují návrh, vývoj a ladění oblastí formuláře.|
|[Návod: Vytvoření prvního doplňku VSTO pro Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)|Ukazuje, jak vytvořit doplněk VSTO pro systém Microsoft Office Outlook.|
|[Outlook 2010 ve vývoji pro Office](http://go.microsoft.com/fwlink/?LinkId=199013)|Oblast knihovny MSDN, kde najdete články a referenční dokumentaci týkající se vývoje řešení Outlooku (netýká se vývoj pro Office pomocí sady Visual Studio).|
