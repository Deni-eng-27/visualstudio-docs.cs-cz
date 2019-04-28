---
title: 'Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.ImportDialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], import a model
- Business Data Connectivity service [SharePoint development in Visual Studio], reuse a model
- BDC [SharePoint development in Visual Studio], import a model
- BDC [SharePoint development in Visual Studio], remove a model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9c10dcf48e5c047778b86c524b35b4e1d5d8cc8a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967050"
---
# <a name="how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project"></a>Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint
  Můžete přizpůsobit, balení a znovu nasadit obchodní Data připojení (BDC) model pomocí sady Visual Studio k přidání souboru modelu (*.bdcm*) do jakéhokoli projektu SharePoint farmu. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

### <a name="to-add-a-bdc-model-file-to-a-sharepoint-project"></a>Přidání souboru modelu služby BDC do projektu služby SharePoint

1. V **Průzkumníka řešení**, vyberte složku pro projekt služby SharePoint.

2. V panelu nabídky zvolte **projektu** > **přidat existující položku**.

3. V **přidat existující položku** dialogové okno, přejděte do umístění souboru definice modelu, který chcete přidat do projektu, vyberte soubor a klikněte na tlačítko **přidat** tlačítko.

    Pokud model nedefinuje *systému řádku obchodní (LOB) typu sestavení .NET*, **objekt LobSystem sestavení .NET přidat** zobrazí se dialogové okno.

4. Pokud se zobrazí dialogové okno, proveďte jednu z následujících kroků:

   - Pokud chcete psát vlastní kód a pomocí návrháře definují metadata pro importovaný model, zvolte **Ano** tlačítko, pojmenujte systému a klikněte na tlačítko **OK** tlačítko.

   - Jinak klikněte na tlačítko **ne** tlačítko a klikněte na tlačítko **OK** tlačítko.

     **Model Připojení obchodních dat** přidání položky do projektu.

## <a name="see-also"></a>Viz také:
- [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Postupy: Vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)
- [Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)
- [Postupy: Zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
