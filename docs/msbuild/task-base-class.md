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
ms.openlocfilehash: 9662a504232c70662e40db54e3eda27aa4abe835
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642960"
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
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Úlohy](../msbuild/msbuild-tasks.md)