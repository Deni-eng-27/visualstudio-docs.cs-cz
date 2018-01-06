---
title: "Sekvenční pracovní postup zobrazení (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 8b54fbb37d33bdb6d4e397c81ad85bffd39b221f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sequential-workflow-views-legacy"></a>Sekvenční pracovní postup zobrazení (zastaralé)
[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]poskytuje starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] který lze použít k cíli [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Poskytuje způsob, jak vytvořit graficky [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace, které používají známé [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uživatelské rozhraní. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]aplikace se skládají z kroků procesu pracovního postupu nazývají aktivity. Pokud chcete vytvořit pracovní postup, tvoří aktivity na návrhovou plochu přetažením návrháře jejich odpovídajících aktivit z **sada nástrojů** na návrhovou plochu.  
  
 Při vytváření sekvenční pracovní postup, který je [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), jsou k dispozici tři zobrazení pracovního postupu. Tato zobrazení jsou k dispozici **pracovního postupu** nabídky a v místní nabídce na návrhovou plochu.  
  
 Následující tabulka uvádí název a popis jednotlivých zobrazení.  
  
|Možnost nabídky nebo karty|Popis|  
|----------------------|-----------------|  
|**Zobrazení sekvenčního pracovního postupu**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **sekvenčního pracovního postupu zobrazení** možnosti v místní nabídce se zobrazí **sekvenční pracovní postup** zobrazení, které zobrazuje podle činností grafického rozhraní reprezentace sekvenčního pracovního postupu. Nebo vyberte **sekvenčního pracovního postupu zobrazení** z **pracovního postupu** nabídky.|  
|**Obslužná rutina zrušit zobrazení**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **obslužná rutina zrušit zobrazení** možnosti v místní nabídce se zobrazí **sekvenční pracovní postup** zobrazení, která ukazuje [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina zrušit zobrazení** z **pracovního postupu** nabídky.|  
|**Obslužná rutina chyb zobrazení**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **obslužná rutina chyb zobrazení** možnosti v místní nabídce se zobrazí **chyb** zobrazení, která ukazuje [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina chyb zobrazení** z **pracovního postupu** nabídky.|  
  
 Další informace o podobné zobrazení najdete v tématu [zobrazení aktivity (zastaralé)](../workflow-designer/activity-views-legacy.md).  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení aktivity (zastaralé)](../workflow-designer/activity-views-legacy.md)   
 [Vytváření projektů pracovního postupu starší verze](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Pracovní postup pro vytváření obsahu režimy](http://go.microsoft.com/fwlink?LinkID=65014)