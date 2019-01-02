---
title: Animace objektů v Návrháři XAML
ms.date: 04/11/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 312721cb47858d3c5462fcbee99289dbad526180
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53941489"
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML

Můžete vytvořit krátké animace, které přesunout objekty nebo má dovnitř a ven vyblednout.

Pokud chcete začít, vytvořte *scénáře*. Scénář obsahuje jeden nebo více *časové osy*. Nastavte *klíčové snímky* na časové ose k označení změny vlastností. Poté při spuštění animace Blendu argument interpolaci změny vlastností za určené časové období. Výsledkem je hladký přechod. Může jakákoli vlastnost, která patří do objektu animace, v případě nevizuální vlastnosti.

Následující obrázek znázorňuje ve scénáři s názvem **MoveUp**. Na časové ose obsahuje klíčové snímky, které označení pozice X a Y obdélníku. Při spuštění této animace obdélníku přesune z jedné pozice do druhé plynule.

![Scénáře MoveUp v Návrháři XAML](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)