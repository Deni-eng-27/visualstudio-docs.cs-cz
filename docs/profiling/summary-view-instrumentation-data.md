---
title: Souhrnné zobrazení – data instrumentace | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 2f52f80cad4ce7678a832a7b76a75d8f2fd4460e
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2019
ms.locfileid: "74778216"
---
# <a name="summary-view---instrumentation-data"></a>Souhrnné zobrazení – data instrumentace
V souhrnném zobrazení se zobrazí informace o nejdražších funkcích, které je náročné při spuštění profilace. Další informace, včetně popisu odkazů na oznámení a seznamů sestav, najdete v tématu [souhrnné zobrazení](../profiling/summary-view.md).

## <a name="timeline-graph"></a>Graf časové osy
 Graf časové osy v zobrazení Souhrn ukazuje využití procesoru profilované aplikací v době, kdy k profilaci došlo. Graf časové osy můžete použít k filtrování zobrazení do vybraného časového rozsahu. Další informace najdete v tématu [Postup: filtrování zobrazení sestav na časové ose souhrnu](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).

## <a name="hot-path"></a>Kritická cesta
 **Cesta k Hotu** zobrazuje cestu spuštění, která spotřebuje nejvíce času. Kliknutím na funkci můžete zobrazit zobrazení podrobností funkce pro danou funkci. Chcete-li zobrazit další zobrazení pro tuto funkci, klikněte na ni pravým tlačítkem myši a potom klikněte na zobrazení v seznamu.

 **Cesta Hot** obsahuje následující data pro každou funkci:

|Sloupec|Popis|
|------------|-----------------|
|**Jméno**|Název funkce|
|**% Uplynulého celkového času**|Procentuální podíl všech časů v datech profilace, které funkce strávila prováděním kódu v těle funkce a ve funkcích, které volal.|
|**% Uplynulého výhradního času**|Procentuální podíl všech časů v datech profilace, které funkce strávila prováděním kódu v těle funkce. Čas strávený ve funkcích, které funkce volala, není zahrnutý.|

## <a name="functions-with-most-individual-work"></a>Funkce s největší individuální prací
 Seznam funkcí, které využily nejaktuálnější čas při provádění kódu v těle funkce a nikoli ve funkcích, které volal.

 **Funkce s většinou individuální práce** obsahuje pro každou funkci následující data:

|Sloupec|Popis|
|------------|-----------------|
|**Jméno**|Název funkce|
|**% Výhradního času**|Procentuální podíl všech časů v datech profilace, které funkce strávila prováděním kódu v těle funkce. Čas strávený ve funkcích, které funkce volala, není zahrnutý.|

## <a name="see-also"></a>Viz také:
- [Souhrnné zobrazení – vzorkování dat](../profiling/summary-view-sampling-data.md)
- [Souhrnné zobrazení – data paměti .NET](../profiling/summary-view-dotnet-memory-data.md)
