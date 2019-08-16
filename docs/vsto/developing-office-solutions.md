---
title: Vývoj řešení pro systém Office
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, about developing solutions
- solutions [Office development in Visual Studio], developing
- Office solutions [Office development in Visual Studio], developing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8ede09f18808eda22c747ac28e3c279fc43266bc
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551573"
---
# <a name="develop-office-solutions"></a>Vývoj řešení pro systém Office
  Po návrhu projektu pomocí nástrojů Office Developer Tools v sadě Visual Studio a nastavení souborů projektu můžete začít soustředit na implementaci kódu a vlastního uživatelského rozhraní (UI).

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="office-solutions-programming-model"></a>Programovací model řešení pro systém Office
 Objektový model Office zpřístupňuje celou řadu objektů, na které můžete programovat. Pokaždé, když budete programovat řešení Office pomocí spravovaného kódu, napíšete kód, který používá typy v primárních sestaveních vzájemné spolupráce pro Office. V řešeních, která vytvoříte pomocí šablon projektů Office v sadě Visual Studio, můžete také napsat kód přímo proti generovaným třídám v projektu. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).

## <a name="program-different-types-of-office-solutions"></a>Programování různých typů řešení pro systém Office
 Typ řešení, které vytváříte, určuje, které funkce můžete v projektu použít. Můžete například přidat ovládací prvky model Windows Forms a rozšířené ovládací prvky Office (pojmenované *ovládací prvky hostitele*) do přizpůsobení na úrovni dokumentu přetažením položek z **panelu nástrojů v sadě** Visual Studio v době návrhu. Pokud ale vyvíjíte doplněk VSTO, můžete do dokumentů za běhu přidat jenom tyto ovládací prvky, a to tak, že napíšete kód.

 Další informace o funkcích, které jsou specifické pro různé typy řešení, naleznete v následujících tématech:

- [Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)

- [Přizpůsobení na úrovni dokumentu programu](../vsto/programming-document-level-customizations.md).

- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md).

  Základní informace, které vám pomůžou plánovat řešení a postupy pro Office, které vám pomůžou vytvářet projekty, najdete v tématu [Návrh a vytváření řešení pro Office](../vsto/designing-and-creating-office-solutions.md).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)|Popisuje různé aspekty psaní kódu v řešeních pro systém Office.|
|[Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)|Poskytuje přehled programovacího modelu doplňků VSTO a souvisejících programovacích úloh.|
|[Přizpůsobení na úrovni dokumentu programu](../vsto/programming-document-level-customizations.md)|Poskytuje přehled programovacího modelu přizpůsobení na úrovni dokumentu a souvisejících programovacích úloh.|
|[Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)|Popisuje různé způsoby, kterými můžete přizpůsobit uživatelské rozhraní aplikací Office pomocí doplňků VSTO a přizpůsobení na úrovni dokumentu.|
|[Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)|Popisuje různé způsoby, jak můžete pracovat s daty v řešeních pro systém Office, například svázat data s ovládacími prvky a ukládat data do mezipaměti v přizpůsobeních na úrovni dokumentu.|
|[Způsob ukládání dopadů na řešení pro systém Office](./how-autosave-impacts-office-solutions.md)|Popisuje úpravy, které může být nutné provést v řešeních Office, pokud je povoleno automatické ukládání.|
|[Řešení potíží s řešeními pro systém Office](../vsto/troubleshooting-office-solutions.md)|Poskytuje tipy pro řešení běžných problémů, se kterými se můžete setkat při vytváření řešení pro Office.|
|[Podpora práce s vlákny v systému Office](../vsto/threading-support-in-office.md)|Poskytuje přehled o práci s více vlákny v řešeních pro systém Office.|
|[Usnadnění v projektech pro systém Office](../vsto/accessibility-in-office-projects.md)|Popisuje funkce pro usnadnění přístupu, které jsou k dispozici v řešeních pro systém Office.|

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvoření a úprava vlastností vlastního dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)
- [Postupy: Číst z a zapisovat do vlastností dokumentu](../vsto/how-to-read-from-and-write-to-document-properties.md)
- [Postupy: Cílení na vícejazyčné uživatelské rozhraní Office](../vsto/how-to-target-the-office-multilingual-user-interface.md)
- [Návod: Vytvoření prvního doplňku VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)
- [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)
- [Návod: Vytvoření prvního doplňku VSTO pro Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)
- [Návod: Vytvoření prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)
- [Návod: Vytvoření prvního doplňku VSTO pro Project](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)
- [Návod: Vytvoření prvního doplňku VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)
- [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)
