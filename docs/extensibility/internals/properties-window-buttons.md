---
title: Tlačítka okna vlastností | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aaa4db159ccb0ecf3d0e9c9243e23fcd0dacc455
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80706177"
---
# <a name="properties-window-buttons"></a>Tlačítka okna Vlastnosti
V závislosti na jazyku vývoje a typu produktu se na panelu nástrojů v okně **vlastnosti** zobrazí určitá tlačítka. Ve všech případech se zobrazí tlačítka **kategorizované**, **Abecední**, **vlastnosti**a **stránky vlastností** . V jazyce Visual C# a Visual Basic se zobrazí také tlačítko **události** . V některých Visual C++ projektech se zobrazí **zprávy VC + +** a VC – tlačítka pro **přepsání** . Další tlačítka mohou být zobrazena pro jiné typy projektů. Další informace o tlačítkách v okně **vlastnosti** naleznete v [okně Vlastnosti](../../ide/reference/properties-window.md).

## <a name="implementation-of-properties-window-buttons"></a>Implementace tlačítek okna vlastností
 Když kliknete na tlačítko **kategorizovat** , Visual Studio zavolá <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> rozhraní objektu, který má fokus na řazení vlastností podle kategorie. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> je implementován na `IDispatch` objektu, který je zobrazen v okně **vlastnosti** .

 K dispozici jsou 11 předdefinované kategorie vlastností, které mají záporné hodnoty. Můžete definovat vlastní kategorie, ale doporučujeme jim přiřadit kladné hodnoty, abyste je rozlišili od předdefinovaných kategorií.

 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A>Metoda vrátí hodnotu odpovídající kategorie vlastnosti pro zadanou vlastnost. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A>Metoda vrátí řetězec, který obsahuje název kategorie. Musíte poskytnout podporu jenom pro vlastní hodnoty kategorií, protože Visual Studio zná standardní hodnoty kategorií vlastností.

 Když kliknete na tlačítko **abecedy** , zobrazí se vlastnosti v abecedním pořadí podle názvu. Názvy jsou načteny `IDispatch` podle lokalizovaného algoritmu řazení.

 Když je okno **vlastnosti** otevřené, tlačítko **vlastnosti** se automaticky zobrazí jako vybrané. V ostatních částech prostředí se zobrazí stejné tlačítko a kliknutím na něj můžete zobrazit okno **vlastnosti** .

 Tlačítko **stránky vlastností** není k dispozici, pokud `ISpecifyPropertyPages` není pro vybraný objekt implementováno. Stránky vlastností zobrazují vlastnosti závislé na konfiguraci, které jsou obvykle spojeny s řešeními a projekty, ale mohou být také přidruženy k položkám projektu (například v Visual C++).

> [!NOTE]
> Do okna **vlastnosti** nelze přidat tlačítka panelu nástrojů pomocí nespravovaného kódu. Chcete-li přidat tlačítko panelu nástrojů, je nutné vytvořit spravovaný objekt, který je odvozen z <xref:System.Windows.Forms.Design.PropertyTab> .

## <a name="see-also"></a>Viz také
- [Rozšíření vlastností](../../extensibility/internals/extending-properties.md)
