---
title: 'Krok 8: Přizpůsobení kvízu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 75bde59c6e4b61c2775f188383fc9058a6c31242
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60109748"
---
# <a name="step-8-customize-the-quiz"></a>Krok 8: Přizpůsobení kvízu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V poslední části tutoriálu prozkoumáte několik způsobů, jak kvíz přizpůsobit a rozšíříte si již nabyté znalosti. Například se zamyslíte nad tím, jak program vytvoří problém náhodného dělení, jehož odpovědí není nikdy zlomek. Další informace, zapněte `timeLabel` určit jinou barvu a dejte účastníkovi kvízu nápovědu.  
  
### <a name="to-customize-the-quiz"></a>Přizpůsobení kvízu  
  
- Když v kvízu zbývá pouze pět sekund, zapněte **timeLabel** řídit červenou nastavením jeho **BackColor** vlastnosti (`timeLabel.BackColor = Color.Red;`). Resetujte barvu, když že kvíz.  
  
- Dejte účastníkovi kvízu nápovědu pomocí přehrání zvuku při zadání správné odpovědi do ovládacího prvku NumericUpDown. (Pro každou událost ovládacího prvku `ValueChanged()` je nutné napsat obslužnou rutinu události, která se vyvolá vždy, když účastník kvízu změní hodnotu ovládacího prvku.)  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematického kvízu](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
- Chcete-li přejít k dalšímu kurzu, přečtěte si téma [Tutorial 3: Vytvořit odpovídající her](../ide/tutorial-3-create-a-matching-game.md).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md).
