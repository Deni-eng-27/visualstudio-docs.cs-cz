---
title: Přehled profilace aktivních skriptů | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Active Script Profiling
ms.assetid: eec2f413-6605-4df4-a86f-4919755e9358
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ce6f7fe29fca2cd17c3dfcce76dac40e422aba4
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572729"
---
# <a name="active-script-profiling-overview"></a>Přehled profilace aktivních skriptů
[Rozhraní profileru aktivních skriptů](../winscript/reference/active-script-profiler-interfaces.md) umožňují profilování skriptovacího stroje. Profilace aktivních skriptů se skládá z následujících částí:  
  
- Jazykový modul  
  
- Hostitel  
  
- profiler  
  
## <a name="language-engine"></a>Jazykový modul  
 Jazykový modul skript spustí. Poskytuje metody, které umožňují profilování kódu skriptu při jeho spuštění. Když je profilace povolená, modul jazyka převezme identifikátor třídy (CLSID) objektu COM profileru jako argument. Vytvoří instanci objektu modelu COM profileru a potom zavolá do profileru, když dojde k různým událostem.  
  
 Jazykový modul implementuje [rozhraní IActiveScriptProfilerControl](../winscript/reference/iactivescriptprofilercontrol-interface.md).  
  
> [!NOTE]
> Modul runtime [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] při vytváření kontroluje proměnnou prostředí JS_PROFILER, aby určil, zda má být povoleno profilování. Pokud je tato proměnná nastavená na CLSID profileru, modul runtime jazyka vytvoří instanci objektu modelu COM profileru pomocí hodnoty proměnné k určení, který Profiler se má vytvořit.  
  
## <a name="host"></a>Hostitel  
 Hostitel vytvoří jazykový modul a poskytuje jazykový modul se skripty, které mají být spuštěny. Inteligentní hostitel také poskytuje kontext dokumentu, který může použít ladicí program nebo profiler k poskytování lepších informací při ladění nebo profilování.  
  
## <a name="profiler"></a>profiler  
 Profiler přijme volání z jazykového modulu, když dojde k různým událostem. Profiler musí být zaregistrován jako objekt modelu COM a musí implementovat rozhraní [rozhraní iactivescriptprofilercallback –](../winscript/reference/iactivescriptprofilercallback-interface.md) .  
  
## <a name="see-also"></a>Viz také:  
 [Rozhraní profileru aktivních skriptů](../winscript/reference/active-script-profiler-interfaces.md)