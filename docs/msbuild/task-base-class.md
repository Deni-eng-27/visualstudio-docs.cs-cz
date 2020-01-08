---
title: Třída Task Base | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b3aaef85c53dfacf592251c95772d17b1a6ff96
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75566394"
---
# <a name="task-base-class"></a>Základní třída úlohy
Mnohé úlohy mají v konečném důsledku dědění z <xref:Microsoft.Build.Utilities.Task> třídy. Tato třída přidá několik parametrů do úkolů, které jsou z nich odvozeny. Tyto parametry jsou uvedeny v tomto dokumentu.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry této základní třídy.

|Parametr|Popis|
|---------------|-----------------|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelný parametr <xref:Microsoft.Build.Framework.IBuildEngine>.<br /><br /> Určuje rozhraní Build Engine dostupné pro úlohy. Modul sestavení automaticky nastaví tento parametr tak, aby umožňoval úkolům volat zpět do něj.|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelný parametr <xref:Microsoft.Build.Framework.IBuildEngine2>.<br /><br /> Určuje rozhraní Build Engine dostupné pro úlohy. Modul sestavení automaticky nastaví tento parametr tak, aby umožňoval úkolům volat zpět do něj.<br /><br /> Toto je vlastnost pohodlí, aby autoři úloh, které dědí z této třídy, nemuseli přetypovat hodnotu z `IBuildEngine` na `IBuildEngine2`.|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelný parametr <xref:Microsoft.Build.Framework.IBuildEngine3>.<br /><br /> Určuje rozhraní modulu sestavení poskytované hostitelem.|
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelný parametr <xref:Microsoft.Build.Framework.ITaskHost>.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Modul sestavení nastavuje tuto vlastnost, pokud má rozhraní IDE hostitele přidružený objekt hostitele s touto konkrétní úlohou.|
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|Volitelný <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Objekt pomocníka protokolování..|

## <a name="see-also"></a>Viz také:
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
- [Úlohy](../msbuild/msbuild-tasks.md)
