---
title: Task – základní třída | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1859694a85b25effe56afef17f65bd831a65882
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54959405"
---
# <a name="task-base-class"></a>Třída base úlohy
Nakonec dědí celou řadu úloh <xref:Microsoft.Build.Utilities.Task> třídy. Tato třída přidává několik parametrů na úlohy, které jsou odvozeny z nich. Tyto parametry jsou uvedeny v tomto dokumentu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry této základní třídy.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine> parametru.<br /><br /> Určuje rozhraní modul sestavení k dispozici pro úlohy. Stroj sestavení automaticky nastaví tento parametr umožnit, aby zpětné volání do ní úlohy.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine2> parametru.<br /><br /> Určuje rozhraní modul sestavení k dispozici pro úlohy. Stroj sestavení automaticky nastaví tento parametr umožnit, aby zpětné volání do ní úlohy.<br /><br /> Toto je vlastnost pohodlí, takže autoři úloh dědění z této třídy nemají k přetypování hodnoty z `IBuildEngine` k `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine3> parametru.<br /><br /> Určuje rozhraní modul sestavení poskytovány tímto hostitelem.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelné <xref:Microsoft.Build.Framework.ITaskHost> parametru.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Stroj sestavení nastaví tuto vlastnost, pokud hostitel integrovaného vývojového prostředí přidružené k objekt hostitele tuto konkrétní úlohu.|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|Volitelné <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Pomocný objekt protokolování...|  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)