---
title: Zobrazení aktivity (zastaralé) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2cc053be2f9d11a9a1f3cd48c6c9d24e366410c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="activity-views-legacy"></a>Zobrazení aktivity (zastaralé)
Řada aktivit poskytované [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)], ze které pracovní postupy se skládá, máte několik zobrazení návrhu v Návrháři pracovních postupů starší verze systému Windows k dispozici. Při přetažení Návrhář aktivity z **sada nástrojů** na návrhovou plochu a následně vždy, když vyberete aktivitu, můžete přepínat mezi různých zobrazení pomocí **pracovního postupu**nabídky nebo kliknutím pravým tlačítkem na vybrané aktivity. Navíc při přesunutí ukazatele nad název vybranou aktivitou, rozevírací seznam sadu karet se zobrazí, můžete přepínat mezi různá zobrazení.

 Každá aktivita má alespoň jedno zobrazení; Toto je výchozí zobrazení zobrazí při přetažení Návrhář aktivity z **sada nástrojů** na návrhovou plochu. Toto zobrazení výchozí aktivity je k dispozici jako **zobrazení [typ aktivity]** možnost nabídkách a na kartě, například **zobrazení paralelní**. Většina aktivity má další zobrazení a různé aktivity může mít různá zobrazení. Například [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) aktivita má kompenzace zobrazení a [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) aktivita má události zobrazení. Řada aktivit, které jsou součástí Windows Workflow Foundation mít **obslužná rutina zrušit zobrazení** a **zobrazení chyb** navrhování pohledů pro zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) a [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) s nimi spojených.

 Následující tabulka uvádí název a popis jednotlivých zobrazení.

|Možnost nabídky nebo karty|Popis|
|----------------------|-----------------|
|**Zobrazení [typ aktivity]**|Vyberte tuto možnost nabídky nebo kartě Zobrazit výchozí grafické znázornění vybranou aktivitou.|
|**Obslužná rutina zrušit zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) spojené s vybranou aktivitou.|
|**Obslužná rutina chyb zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) spojené s vybranou aktivitou.|
|**Obslužná rutina kompenzace zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) spojené s vybranou [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093).|
|**Obslužnou rutinu události zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) spojené s vybranou [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030).|

 Informace o podobné zobrazení najdete v tématu [sekvenční pracovní postup zobrazení (zastaralé)](../workflow-designer/sequential-workflow-views-legacy.md).

## <a name="see-also"></a>Viz také

- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)
- [Zobrazení sekvenčního pracovního postupu (starší verze)](../workflow-designer/sequential-workflow-views-legacy.md)