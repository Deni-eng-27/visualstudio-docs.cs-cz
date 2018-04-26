---
title: 'Krok 8: Přizpůsobení kvízu'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82e059383a706c45e6882b97611f680a3d49baeb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-8-customize-the-quiz"></a>Krok 8: Přizpůsobení kvízu
V poslední části tutoriálu prozkoumáte několik způsobů, jak kvíz přizpůsobit a rozšíříte si již nabyté znalosti. Například se zamyslíte nad tím, jak program vytvoří problém náhodného dělení, jehož odpovědí není nikdy zlomek. Další informace, zapněte `timeLabel` řízení barvu a poskytněte příjemce kvízu s časovým limitem nápovědu.  

### <a name="to-customize-the-quiz"></a>Přizpůsobení kvízu  

-   Když pouze pět sekund, zůstanou v kvízu, zapněte **timeLabel** řídit nastavení red jeho **BackColor** vlastnost (`timeLabel.BackColor = Color.Red;`). Barva resetujte, když kvízu nad.  

-   Dejte účastníkovi kvízu nápovědu pomocí přehrání zvuku při zadání správné odpovědi do ovládacího prvku NumericUpDown. (Pro každou událost ovládacího prvku `ValueChanged()` je nutné napsat obslužnou rutinu události, která se vyvolá vždy, když účastník kvízu změní hodnotu ovládacího prvku.)  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Si můžete stáhnout dokončenou verzi kvízu [dokončení matematického kvízu kurz ukázka](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  

-   Pokud chcete přejít na další kurzu, přečtěte si téma [kurzu 3: vytvoření hry s odpovídajícím](../ide/tutorial-3-create-a-matching-game.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 7: problémy přidat násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md).
