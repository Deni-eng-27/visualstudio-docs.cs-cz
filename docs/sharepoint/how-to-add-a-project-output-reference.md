---
title: 'Postupy: Přidání odkazu na výstup projektu | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bea0f39ae161d8b695f872cb634c35d0cb205c91
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "86016757"
---
# <a name="how-to-add-a-project-output-reference"></a>Postupy: Přidání odkazu na výstup projektu
  Chcete-li nasadit sestavení projektu jiného typu než SharePoint (nebo soubory. xap v projektech Silverlight) do služby SharePoint, přidejte je jako výstupní odkaz projektu.

 Tento proces vytvoří závislost sestavení řešení mezi těmito dvěma projekty. Projekty spojené s odkazy na výstup projektu jsou sestaveny před sestavením a nasazením projektu služby SharePoint.

### <a name="to-add-a-project-output-reference"></a>Přidání odkazu na výstup projektu

1. Načtěte řešení, které obsahuje alespoň jeden projekt služby SharePoint a jeden projekt, který není projektem služby SharePoint.

2. V **Průzkumník řešení**vyberte položku v uzlu projektu služby SharePoint.

3. V okně **vlastnosti** zvolte vlastnost **výstupní odkazy projektu** a potom klikněte na tlačítko se třemi tečkami (![Elipsa ASP.NET Mobile Designer](../sharepoint/media/mwellipsis.gif "Elipsa ASP.NET Mobile Designer")) vedle ní.

4. V dialogovém okně **výstupní odkazy projektu** klikněte na tlačítko **Přidat** .

5. V podokně Vlastnosti klikněte na šipku vedle vlastnosti **typ nasazení** a pak zvolte vhodnou hodnotu pro položku, na kterou odkazujete, například **ElementFile**.

6. Zvolte šipku vedle pole **název projektu**, zvolte název položky projektu mimo službu SharePoint a pak klikněte na tlačítko **OK** .

## <a name="see-also"></a>Viz také
- [Poskytnutí informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
- [Postupy: označení ovládacích prvků jako bezpečných ovládacích prvků](../sharepoint/how-to-mark-controls-as-safe-controls.md)
- [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
