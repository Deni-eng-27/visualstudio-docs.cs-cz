---
title: 'Postupy: určení prvního cíle k sestavení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- DefaultTargets attribute [MSBuild]
- MSBuild, specifying the defalut target
- MSBuild, DefaultTargets attribute
ms.assetid: a580ba5b-2919-42d2-ae38-1af991e0205a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e812be4927ee0232d1096fa272d8ff8e7358366
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2018
ms.locfileid: "39078797"
---
# <a name="how-to-specify-which-target-to-build-first"></a>Postupy: Zadejte které se zaměřují na nejdřív sestavit
Soubor projektu může obsahovat jednu nebo více `Target` prvky, které definují, jak je sestaven projekt. [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) Modulu sestavení první ho najde a projektu všechny závislosti, pokud soubor projektu obsahuje `DefaultTargets` atribut, `InitialTargets` atribut nebo cíl je zadán v příkazovém řádku pomocí **/ Cíl** přepnout.  
  
## <a name="use-the-initialtargets-attribute"></a>Použijte atribut InitialTargets  
 `InitialTargets` Atribut `Project` prvek určuje cíl, který bude spuštěn jako první, i když cíle jsou zadány v příkazovém řádku nebo v `DefaultTargets` atribut.  
  
#### <a name="to-specify-one-initial-target"></a>Chcete-li určit jeden počáteční cíl  
  
-   Zadejte výchozí cíl v `InitialTargets` atribut `Project` elementu. Příklad:  
  
     `<Project InitialTargets="Clean">`  
  
 Můžete zadat více než jeden počáteční cíl v `InitialTargets` atribut seznam cílů v pořadí a použitím středníkem oddělte každý cíl. Cíle v seznamu se spustí sekvenčně.  
  
#### <a name="to-specify-more-than-one-initial-target"></a>Chcete-li zadat více než jeden počáteční cíl  
  
-   Počáteční cíle, oddělené středníky, v seznamu `InitialTargets` atribut `Project` elementu. Například pro spuštění `Clean` target a pak `Compile` cílové, zadejte:  
  
     `<Project InitialTargets="Clean;Compile">`  
  
## <a name="use-the-defaulttargets-attribute"></a>Použití defaulttargets – atribut  
 `DefaultTargets` Atribut `Project` element určuje, které cíl nebo cíle jsou sestaveny Pokud cíl není explicitně zadána na příkazovém řádku. Pokud cíle jsou určené v i `InitialTargets` a `DefaultTargets` atributy a žádný cíl je zadán v příkazovém řádku [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] cíle zadané ve spuštění `InitialTargets` za nímž následuje cíle zadané v atributu `DefaultTargets` atribut.  
  
#### <a name="to-specify-one-default-target"></a>Chcete-li zadat jeden výchozí cíl  
  
-   Zadejte výchozí cíl v `DefaultTargets` atribut `Project` elementu. Příklad:  
  
     `<Project DefaultTargets="Compile">`  
  
 Můžete zadat více než jeden výchozí cíl v `DefaultTargets` atribut seznam cílů v pořadí a použitím středníkem oddělte každý cíl. Cíle v seznamu se spustí sekvenčně.  
  
#### <a name="to-specify-more-than-one-default-target"></a>Chcete-li zadat více než jeden výchozí cíl  
  
-   Výchozí cíle, oddělené středníky, v seznamu `DefaultTargets` atribut `Project` elementu. Například pro spuštění `Clean` target a pak `Compile` cílové, zadejte:  
  
     `<Project DefaultTargets="Clean;Compile">`  
  
## <a name="use-the-target-switch"></a>Použijte parametr/target přepínače  
 Pokud není definován výchozí cíl v souboru projektu, nebo pokud nechcete používat, které se zaměřují výchozí, můžete použít přepínač příkazového řádku **/target** určit jiný cíl. Cíl nebo cíle zadané s **/target** přepínače se spustí místo cíle, které jsou určené `DefaultTargets` atribut. Podle cílů `InitialTargets` atribut vždy spouští jako první.  
  
#### <a name="to-use-a-target-other-than-the-default-target-first"></a>Nejprve použít jiný cíl než výchozí cíl  
  
-   Zadejte cíl jako první použití cílové **/target** přepínač příkazového řádku. Příklad:  
  
     `msbuild file.proj /target:Clean`  
  
#### <a name="to-use-several-targets-other-than-the-default-targets-first"></a>Nejprve použít několik cílů jiné než výchozí cíle  
  
-   Seznam cílů, oddělené středníky nebo čárkami, pomocí **/target** přepínač příkazového řádku. Příklad:  
  
     `msbuild <file name>.proj /t:Clean;Compile`  
  
## <a name="see-also"></a>Viz také:
  [MSBuild](../msbuild/msbuild.md)  
 [Cíle](../msbuild/msbuild-targets.md)   
 [Postupy: Vyčištění sestavení](../msbuild/how-to-clean-a-build.md)
