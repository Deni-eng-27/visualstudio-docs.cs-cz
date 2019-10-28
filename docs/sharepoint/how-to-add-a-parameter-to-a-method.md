---
title: 'Postupy: Přidání parametru do metody | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: eb1a1c1e8f11ac6daa46f9fe1468a1ff3509e135
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2019
ms.locfileid: "72986228"
---
# <a name="how-to-add-a-parameter-to-a-method"></a>Postupy: Přidání parametru do metody
  Použijte parametr pro předání informací do metody nebo pro vrácení informací z metody. Všechny metody musí mít alespoň jeden parametr. Další informace o tom, jak navrhnout parametr pro podporu typu metody, kterou chcete vytvořit, najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

 Když přidáte parametr do metody, Visual Studio přidá element Parameter do XML souboru modelu v projektu. Další informace o atributech elementu parametru naleznete v tématu [Parameter](/previous-versions/office/developer/sharepoint-2010/ee557705(v=office.14)).

### <a name="to-add-a-parameter-to-a-method"></a>Přidání parametru do metody

1. Přidejte do entity metodu.

2. Na panelu nabídek vyberte možnost **zobrazit** > **Další Windows** > **Podrobnosti metody služby BDC**.

     Otevře se okno **Podrobnosti metody služby BDC** . Další informace najdete v tématu [Přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V okně **Podrobnosti metody služby BDC** rozbalte uzel metody a potom rozbalte uzel **parametry** .

4. V seznamu **Přidat parametr** vyberte možnost **vytvořit parametr**.

     Nový parametr se zobrazí pod uzlem **parametry** .

5. Na panelu nabídek vyberte možnost **zobrazit** > **okno Vlastnosti**.

6. V okně **vlastnosti** nastavte vlastnost **název** na libovolný název, který dává smysl. Například pokud bude metoda vracet zákazníky, můžete pojmenovat metodu **GetCustomers**.

7. V okně **Podrobnosti metody služby BDC** otevřete seznam, který se zobrazí pro směr parametru, a pak zvolte **in**, **InOut**, **out**nebo **return**.

     Další informace o tom, jaký směr chcete zvolit pro metodu typu, kterou vytváříte, najdete v tématu [Návrh modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

8. Upravte popisovač typu parametru. Další informace naleznete v tématu [How to: define a Type deskriptor parametru](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

## <a name="see-also"></a>Viz také:
- [Přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [Postupy: definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Postupy: definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
- [Návrh modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
