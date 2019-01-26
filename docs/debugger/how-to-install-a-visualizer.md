---
title: 'Postupy: Instalace Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6e2ff65e5d410295e9ce7fa0512588b68ca25e55
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54965533"
---
# <a name="how-to-install-a-visualizer"></a>Postupy: Instalace Vizualizéru
Po vytvoření vizualizéru, musíte nainstalovat vizualizéru tak, že bude k dispozici v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Instalace vizualizéru je jednoduchý proces.  
  
> [!NOTE]
>  V aplikacích pro UPW, pouze standardní text, HTML, XML a JSON vizualizéry jsou podporovány. Vizualizéry vlastní (uživatelem vytvořené) nejsou podporovány.  
  
### <a name="to-install-a-visualizer"></a>Instalace vizualizéru  
  
1.  Vyhledejte knihovnu DLL, která obsahuje vizualizaci, kterou jste vytvořili.  
  
2.  Kopie knihovny DLL některou z následujících umístění:  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  Pokud chcete používat spravované vizualizéru pro vzdálené ladění, zkopírujte knihovnu DLL do stejného umístění na vzdáleném počítači.  
  
4.  Restartujte relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)   
 [Postupy: Zápis vizualizéru](/visualstudio/debugger/create-custom-visualizers-of-data)