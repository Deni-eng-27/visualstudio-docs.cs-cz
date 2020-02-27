---
title: 'Postupy: určení cíle, který se má sestavit jako první | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- DefaultTargets attribute [MSBuild]
- MSBuild, specifying the defalut target
- MSBuild, DefaultTargets attribute
ms.assetid: a580ba5b-2919-42d2-ae38-1af991e0205a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e008e3181cd7c633179f35e7639265a2495fafe2
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77633795"
---
# <a name="how-to-specify-which-target-to-build-first"></a>Postupy: určení prvního cíle sestavení

Soubor projektu může obsahovat jeden nebo více `Target` prvků, které definují, jak je projekt sestaven. Modul Microsoft Build Engine (MSBuild) sestaví první projekt, který najde, a všechny závislosti, pokud soubor projektu neobsahuje atribut `DefaultTargets`, `InitialTargets` atribut nebo cíl je zadán na příkazovém řádku pomocí přepínače **-target** .
## <a name="use-the-initialtargets-attribute"></a>Použití atributu InitialTargets

 Atribut `InitialTargets` elementu `Project` určuje cíl, který se spustí jako první, a to i v případě, že jsou cíle zadány na příkazovém řádku nebo v atributu `DefaultTargets`.
Atribut `InitialTargets` elementu `Project` určuje cíl, který se spustí jako první, a to i v případě, že jsou cíle zadány na příkazovém řádku nebo v atributu `DefaultTargets`.

#### <a name="to-specify-one-initial-target"></a>Určení jednoho počátečního cíle

- Zadejte výchozí cíl v atributu `InitialTargets` elementu `Project`. Příklad:

   `<Project InitialTargets="Clean">`

  Můžete zadat více než jeden počáteční cíl v atributu `InitialTargets` zobrazením cílů v pořadí a použitím středníku pro oddělení jednotlivých cílů. Cíle v seznamu se spustí postupně.

#### <a name="to-specify-more-than-one-initial-target"></a>Určení více než jednoho počátečního cíle

- Seznam počátečních cílů oddělených středníky v atributu `InitialTargets` elementu `Project`. Pokud například chcete spustit cíl `Clean` a potom `Compile` cíl, zadejte:

     `<Project InitialTargets="Clean;Compile">`

## <a name="use-the-defaulttargets-attribute"></a>Použití atributu DefaultTargets –

 Atribut `DefaultTargets` elementu `Project` určuje, který cíl nebo cíle jsou vytvořeny, pokud cíl není explicitně zadán na příkazovém řádku. Pokud jsou cíle zadány v atributech `InitialTargets` a `DefaultTargets` a v příkazovém řádku není zadán žádný cíl, nástroj MSBuild spustí cíle zadané v atributu `InitialTargets` následovaný cíli určenými v atributu `DefaultTargets`.

#### <a name="to-specify-one-default-target"></a>Určení jednoho výchozího cíle

- Zadejte výchozí cíl v atributu `DefaultTargets` elementu `Project`. Příklad:

   `<Project DefaultTargets="Compile">`

  Můžete zadat více než jeden výchozí cíl v atributu `DefaultTargets` uvedením cílů v pořadí a použitím středníku pro oddělení jednotlivých cílů. Cíle v seznamu se spustí postupně.

#### <a name="to-specify-more-than-one-default-target"></a>Určení více než jednoho výchozího cíle

- Seznam výchozích cílů oddělených středníky v atributu `DefaultTargets` elementu `Project`. Pokud například chcete spustit cíl `Clean` a potom `Compile` cíl, zadejte:

     `<Project DefaultTargets="Clean;Compile">`

## <a name="use-the--target-switch"></a>Použití přepínače-target

 Pokud v souboru projektu není definován výchozí cíl, nebo pokud nechcete použít tento výchozí cíl, můžete zadat jiný cíl pomocí příkazu pro přepínač příkazového řádku **target** . Cíl nebo cíle zadané s přepínačem **target** jsou spuštěny namísto cílů určených atributem `DefaultTargets`. Cíle zadané v atributu `InitialTargets` vždy spouštějí jako první.

#### <a name="to-use-a-target-other-than-the-default-target-first"></a>Použití cíle jiného než výchozího cíle

- Zadejte cíl jako první cíl pomocí přepínače příkazového řádku **-target** . Příklad:

     `msbuild file.proj -target:Clean`

#### <a name="to-use-several-targets-other-than-the-default-targets-first"></a>Použití několika cílů kromě výchozích cílů

- Seznam cílů oddělených středníky nebo čárkami pomocí přepínače příkazového řádku **-target** . Příklad:

     `msbuild <file name>.proj -t:Clean;Compile`

## <a name="see-also"></a>Viz také

- [MSBuild](../msbuild/msbuild.md)
- [Cíle](../msbuild/msbuild-targets.md)
- [Postupy: vyčištění sestavení](../msbuild/how-to-clean-a-build.md)
