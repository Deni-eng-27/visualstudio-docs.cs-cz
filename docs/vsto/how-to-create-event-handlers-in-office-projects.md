---
title: 'Postupy: vytváření obslužných rutin událostí v projektech pro systém Office'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee85d89dcb990cebd595dadbd7b28add4a7b371a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538304"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Postupy: vytváření obslužných rutin událostí v projektech pro systém Office
  Existuje několik způsobů, jak vytvořit obslužné rutiny událostí v Visual Basic a C#. V zobrazení Návrh můžete vytvořit výchozí obslužné rutiny událostí pro ovládací prvky Poklikáním na ovládací prvek nebo pomocí podokna události v okně **vlastnosti** vytvořit obslužné rutiny pro libovolnou událost ovládacího prvku. Nicméně pokud jste v zobrazení kódu, možná nebudete chtít přepnout na zobrazení Návrh a vytvořit obslužnou rutinu události.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-create-an-event-handler-in-visual-basic"></a>Vytvoření obslužné rutiny události v Visual Basic

1. V rozevíracím seznamu **název třídy** v horní části editoru kódu vyberte objekt, pro který chcete vytvořit obslužnou rutinu události.

    > [!NOTE]
    > Pokud chcete vytvořit obslužné rutiny události pro `ThisDocument` nebo `ThisWorkbook` , musíte vybrat **(události ThisDocument)** nebo **(události ThisWorkbook)** v rozevíracím seznamu **název třídy** .

2. V rozevíracím seznamu **název metody** v horní části editoru kódu vyberte událost.

     Visual Studio vytvoří obslužnou rutinu události a přesune bod vložení do nově vytvořené obslužné rutiny události. Pokud obslužná rutina události již existuje, přesune se bod vložení do existující obslužné rutiny události.

### <a name="to-create-an-event-handler-in-c"></a>Vytvoření obslužné rutiny události v jazyce C\#

1. Vytvořte delegáta události ve **spouštěcí** události třídy zadáním kvalifikovaného názvu události následovaného mezerou a potom zadejte **+=** bez mezer. Příklad:

     `this.<object name>.<event name> +=`

2. Na konci řádku kódu stiskněte dvakrát klávesu TAB.

     Visual Studio automaticky dokončí řádek kódu, vytvoří obslužnou rutinu události a přesune bod vložení do nově vytvořené obslužné rutiny události.

## <a name="see-also"></a>Viz také
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)
- [Návod: program na události ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Sestavování řešení pro systém Office](../vsto/building-office-solutions.md)
