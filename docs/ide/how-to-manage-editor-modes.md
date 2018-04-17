---
title: Visual studio celoobrazovkový režim a režim virtuálního prostoru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22c303dd662cac2af4df8652bf001b4b699b23ca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manage-editor-modes"></a>Postupy: Správa režimů editoru
Editor kódu aplikace Visual Studio můžete zobrazit v různých režimech zobrazení.  
  
> [!NOTE]
> Dialogová okna a příkazy nabídky, které vidíte mohou lišit od těch popsaných v tomto článku v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje**, **nastavení importu a exportu**a potom Zvolte **obnovit nastavení**.
  
## <a name="enabling-full-screen-mode"></a>Povolení režim celé obrazovky  
Můžete skrýt všechny okna nástrojů a zobrazit pouze dokumentu windows povolením **celé obrazovky** režimu.  
  
#### <a name="to-enable-full-screen-mode"></a>Pokud chcete povolit režim celé obrazovky  
  
-   Stiskněte klávesu **Alt**+**Shift**+**Enter** zadejte nebo ukončete **celé obrazovky** režimu.  
  
     --nebo--  
  
-   Vydejte příkaz `View.Fullscreen` v **příkaz** okno.  
  
## <a name="enabling-virtual-space-mode"></a>Povolení režim virtuálního prostoru  
V **virtuální adresní prostor** režim, jsou vloženy mezery na konci každého řádku kódu. Vyberte tuto možnost na pozici komentáře ve stejném místě vedle vašeho kódu.  
  
#### <a name="to-enable-virtual-space-mode"></a>Pokud chcete povolit režim virtuálního prostoru  
  
1.  Vyberte **možnosti** z **nástroje** nabídky.

2.  Rozbalte **textového editoru** složku a zvolte **všechny jazyky** globálně nastavit tuto možnost, nebo vyberte složku, konkrétní jazyk. Například zapnout čísla řádků pouze v jazyce Visual Basic, vyberte uzel základní, textový Editor.
  
3.  Vyberte **Obecné** možnosti a v části **nastavení**, vyberte **povolit virtuální prostor**.  
  
    > [!NOTE]
    >  **Virtuální prostor** je povolena v **sloupců výběru** režimu. Když **virtuální adresní prostor** není povolen režim, přesune jako kurzor od konce jeden řádek přímo na první znak na další.  
  
## <a name="see-also"></a>Viz také
[Přizpůsobení editoru](../ide/customizing-the-editor.md)   
[Přizpůsobení rozložení oken v sadě Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md)   
[Písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)