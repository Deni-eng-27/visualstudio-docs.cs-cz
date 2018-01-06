---
title: "Postupy: vytvoření dědičnosti mezi typy (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b939da3ae4020cc6412f9b1767d5bef8bce05472
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-inheritance-between-types-class-designer"></a>Postupy: vytvoření dědičnosti mezi typy (návrhář tříd)
Pokud chcete vytvořit vztah dědičnosti mezi dvěma typy v diagramu tříd pomocí návrháře tříd, připojení základní typ s jeho odvozený typ nebo typy. Můžete mít vztah dědičnosti mezi dvěma třídami, mezi třídy a rozhraní nebo mezi dvě rozhraní.  
  
### <a name="to-create-an-inheritance-between-types"></a>Chcete-li vytvořit dědičnosti mezi typy  
  
1.  Ze svého projektu v Průzkumníku řešení otevřete soubor třídy diagram (.cd).  
  
     Pokud nemáte diagramu tříd, vytvořte ho. V tématu [postupy: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).  
  
2.  V **sada nástrojů**v části **návrhář tříd**, klikněte na tlačítko **dědičnosti**.  
  
3.  Na diagramu tříd kreslení řádku s dědičnosti mezi typy, které chcete, od:  
  
    -   Odvozené třídy za účelem základní třídy  
  
    -   Implementující třídu rozhraní implementované  
  
    -   Rozšíření rozhraní rozšířené rozhraní  
  
4.  Případně pokud máte odvozený typ od obecného typu, klikněte na řádek dědičnosti. V **vlastnosti** nastavte **argumenty typu** vlastnost, která má odpovídat typ, který chcete použít pro obecný typ.  
  
    > [!NOTE]
    >  Pokud nadřazená abstraktní třída obsahuje nejméně jeden člen abstraktní, jsou implementované všechny abstraktní členy jako dědičných neabstraktní třídy.  
    >   
    >  I když můžete vizualizovat existující obecné typy, nelze vytvořit nové obecné typy. Parametry typu pro existující obecné typy také nelze změnit.  
  
## <a name="see-also"></a>Viz také
[Dědičnost](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)   
[Základní informace o dědičnosti](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
[Postupy: zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)   
[Třídy jazyka Visual C++ v Návrháři tříd](visual-cpp-classes.md)