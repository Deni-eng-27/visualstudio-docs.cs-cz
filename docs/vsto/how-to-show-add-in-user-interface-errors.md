---
title: 'Postupy: zobrazení chyb uživatelského rozhraní doplňku'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 49985589c021192454bf0dd58929c9ef5646aec9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545779"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Postupy: zobrazení chyb uživatelského rozhraní doplňku
  Ve výchozím nastavení platí, že pokud se doplněk VSTO pokusí manipulovat s systém Microsoft Office uživatelském rozhraní (UI) a chyba, nezobrazí se žádná chybová zpráva. Můžete ale nakonfigurovat aplikace systém Microsoft Office, aby zobrazovaly zprávy o chybách, které se vztahují k uživatelskému rozhraní. Tyto zprávy můžete použít k určení, proč se nezobrazí vlastní pás karet, nebo proč se pás karet zobrazí, ale nezobrazí se žádné ovládací prvky.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

## <a name="to-show-vsto-add-in-user-interface-errors"></a>Zobrazení chyb uživatelského rozhraní doplňku VSTO

1. Spusťte aplikaci.

2. Klikněte na kartu **soubor** .

3. Klikněte na tlačítko **Možnosti**.

4. V podokně kategorie klikněte na **Upřesnit**.

5. V podokně podrobností vyberte možnost **Zobrazit chyby uživatelského rozhraní doplňku VSTO**a pak klikněte na tlačítko **OK**.

    > [!NOTE]
    > V případě aplikace Outlook je zaškrtávací políčko **Zobrazit chyby uživatelského rozhraní doplňku VSTO** umístěno v části **vývojář** v podokně podrobností. U ostatních aplikací se zaškrtávací políčko nachází v části **Obecné** v podokně podrobností.

## <a name="see-also"></a>Viz také
- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)
- [Vytvoření oblastí formuláře aplikace Outlook](../vsto/creating-outlook-form-regions.md)
- [Přehled pásu karet](../vsto/ribbon-overview.md)
- [Přehled podokna akcí](../vsto/actions-pane-overview.md)
