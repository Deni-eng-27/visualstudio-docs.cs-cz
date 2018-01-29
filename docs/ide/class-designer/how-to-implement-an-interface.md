---
title: "Postupy: implementace rozhraní (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 819fdb15a436dbdb4059d7ecef3e23d95c0aebe4
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-implement-an-interface-class-designer"></a>Postupy: Implementace rozhraní (návrhář tříd)
V Návrháři tříd je možné implementovat rozhraní v diagramu tříd propojením na třídu, která obsahuje kód pro metody rozhraní. Návrhář tříd generuje implementace rozhraní a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslení řádku s dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.  
  
> [!TIP]
>  Můžete vytvořit rozhraní stejným způsobem jako vytvoříte jiné typy. Pokud jste rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejdřív zobrazte. Další informace najdete v tématu [postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md) a [postupy: zobrazení existujících typů](how-to-view-existing-types.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>K implementaci rozhraní podle kreslení řádku s dědičnosti  
  
1.  Na diagramu tříd zobrazení rozhraní a třídy, která implementuje rozhraní.  
  
2.  Zakreslit řádku s dědění ze třídy a rozhraní.  
  
     Typu Lupa se zobrazí připojené k třídě a štítek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje zástupných procedur pro všechny členy rozhraní.  
  
 Další informace najdete v tématu [postupy: vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>K implementaci rozhraní z okna zobrazení tříd  
  
1.  V diagramu tříd zobrazení třídu, která chcete implementovat rozhraní.  
  
2.  Otevřete zobrazení tříd a vyhledejte rozhraní.  
  
    > [!TIP]
    > Pokud zobrazení tříd není otevřený, otevřete zobrazení tříd z **zobrazení** nabídky.
  
3.  Přetáhněte uzel rozhraní tvar – třída v diagramu.  
  
     Typu Lupa se zobrazí připojené k třídě a štítek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje zástupných procedur pro všechny členy rozhraní; v tomto okamžiku se implementuje rozhraní.  
  
## <a name="see-also"></a>Viz také
[Postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md)   
[Postupy: zobrazení existujících typů](how-to-view-existing-types.md)   
[Postupy: vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)   
[Refaktoring tříd a typů](refactoring-classes-and-types.md)