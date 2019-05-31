---
title: 'Návrhář pracovního postupu: Ladění XAML'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 0d22668089581dcf44609756a4e7f8f4527dd751
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/31/2019
ms.locfileid: "66431814"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Postupy: Ladění XAML pomocí návrháře postupu provádění

Pracovní postupy jsou definována v XAML. Uživatelské rozhraní reprezentace pracovního postupu je nástavbou stromu XAML definování pracovního postupu. Možnosti ladění je podobné ladění pracovních postupů v Návrháři pracovních postupů. Například při ladění XAML, místní hodnoty, kukátko a vlákna windows fungovat stejným způsobem jako stejně jako v Návrháři postupu provádění ladění. Kromě toho zobrazení zásobníku volání během ladění XAML je založené na řádku hierarchické zobrazení toku provádění pracovního postupu.

> [!NOTE]
> Pokud XAML pro pracovní postup je umístěn ve stejném sestavení, aktivity, část sestavení pro názvy tříd nejsou zahrnuty. Bez této části názvy tříd (aktivita) nelze načíst XAML za běhu. Nedoporučuje se definovat aktivity v stejný obor názvů jako hlavní projektu. v opačném případě XAML bude potřeba ručně upravit po upravována v návrháři.

## <a name="to-debug-workflow-xaml"></a>Chcete-li ladit pracovní postup XAML

1. Otevřete projekt pracovního postupu nebo aktivity v sadě Visual Studio.

2. Nastavit zarážku na aktivitu nebo aktivity, který chcete ladit, jak je popsáno v [jak: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md).

3. Klikněte pravým tlačítkem na soubor .xaml, který obsahuje definici pracovního postupu a vyberte **zobrazit kód**. Zobrazí se zarážku na stejném řádku jako deklarace prvku XAML, které jste nastavili zarážku na v návrhovém zobrazení aktivity.

4. Vyvolání ladicího programu, jak je popsáno v [ladění pracovních postupů](debugging-workflows-with-the-workflow-designer.md).

5. Při provádění kódu dosáhnou některé z vašich zarážek, budou zvýrazněny elementu XAML přidružené k této zarážky. Chcete-li přejít k další zarážce, použijte **F10** nebo **F11** klíč.

## <a name="see-also"></a>Viz také:

- [Postupy: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Ladění pracovních postupů](debugging-workflows-with-the-workflow-designer.md)