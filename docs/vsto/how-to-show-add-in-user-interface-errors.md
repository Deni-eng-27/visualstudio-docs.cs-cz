---
title: 'Postupy: Zobrazení doplňku uživatele chyb rozhraní'
ms.date: 02/02/2017
ms.topic: conceptual
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
ms.openlocfilehash: 466b316340f922d13ed559791d1340912c4cecfd
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862912"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Postupy: Zobrazení doplňku uživatele chyb rozhraní
  Ve výchozím nastavení pokud doplňku VSTO pokusí pracovat s Microsoft Office uživatelského rozhraní (UI) a selže, žádná se chybová zpráva. Můžete ale nakonfigurovat aplikace Microsoft Office pro zobrazení zprávy pro chyby, které se vztahují na uživatelské rozhraní. Tyto zprávy můžete použít k určení toho, proč se nezobrazí vlastní pás karet nebo proč se zobrazí pásu karet, ale žádné ovládací prvky se zobrazí.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="to-show-vsto-add-in-user-interface-errors"></a>K zobrazení chyb rozhraní uživatele doplňku VSTO  
  
1.  Spusťte aplikaci.  
  
2.  Klikněte na tlačítko **souboru** kartu.  
  
3.  Klikněte na tlačítko **možnosti**.  
  
4.  V podokně kategorie, klikněte na tlačítko **Upřesnit**.  
  
5.  V podokně podrobností vyberte **doplňku VSTO zobrazení chyb uživatelského rozhraní**a potom klikněte na tlačítko **OK**.  
  
    > [!NOTE]  
    >  Pro aplikaci Outlook **doplňku VSTO zobrazení chyb uživatelského rozhraní** zaškrtávacího políčka se nachází v **Developer** části podokna podrobností. U ostatních aplikací se nachází na zaškrtávací políčko v **Obecné** části podokna podrobností.  
  
## <a name="see-also"></a>Viz také:  
 [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)  
