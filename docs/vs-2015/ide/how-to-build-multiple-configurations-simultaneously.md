---
title: 'Postupy: Sestavení více konfigurací současně | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 16a509c5a8fa46620e60fb5f1497c38d97ff6330
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068311"
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Postupy: Sestavení více konfigurací současně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Většina typů projektů s několika, nebo dokonce i všechny jejich konfigurace sestavení ve stejnou dobu můžete vytvářet pomocí **dávkové sestavení** dialogové okno. Však nemůže vytvořit následující typy projektů v několika konfiguracích sestavení ve stejnou dobu:  
  
1. [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace vytvořené pro Windows pomocí jazyka JavaScript.  
  
2. Všechny projekty jazyka Visual Basic.  
  
   Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>Sestavení projektu v několika konfiguracích sestavení  
  
1. V panelu nabídky zvolte **sestavení**, **dávkové sestavení**.  
  
2. V **sestavení** sloupce, vyberte zaškrtávací políčka pro konfigurace, ve kterých chcete sestavit projekt.  
  
    > [!TIP]
    >  Chcete-li upravit nebo vytvořit vlastní proces sestavení pro řešení, zvolte **sestavení**, **nástroje Configuration Manager** na řádku nabídek otevřete **nástroje Configuration Manager** dialogové okno. Po úpravě konfigurace sestavení řešení, zvolte **znovu sestavit** tlačítko **dávkové sestavení** dialogové okno s aktualizací všech sestavení konfigurací pro projekty v řešení.  
  
3. Zvolte **sestavení** nebo **znovu sestavit** tlačítka pro vytvoření projektu s konfiguracemi, které jste zadali.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)   
 [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
 [Paralelní sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
