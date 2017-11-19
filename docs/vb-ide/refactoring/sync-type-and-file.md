---
title: "Synchronizovat typ a název souboru - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff86d7bd-837b-4664-b0ea-d3ee0c52fe87
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.openlocfilehash: da6f39dd3573d361c1da579eb3d84c2c8ceeb517
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>Synchronizovat typu pro název souboru nebo název souboru na typ v jazyce Visual Basic

<!-- VERSIONLESS -->
**Tato funkce je k dispozici v aplikaci Visual Studio 2017 a novějším.  Kromě toho se pro tento refaktoring ještě nepodporuje .NET Standard projekty.**

**Co:** umožňuje přejmenujte typ k porovnání název souboru, nebo název souboru tak, aby odpovídaly typ obsahuje.

**Kdy:** přejmenovaná souboru nebo typ a ještě neprovedli aktualizaci na odpovídající soubor nebo typ k porovnání. 

**Důvod:** umístění a typ v souboru s jiným názvem nebo naopak, je obtížné najít, co hledáte.  Přejmenováním typ nebo název souboru, bude kód čitelnější a snadný přechod.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název typu synchronizovat:

   ![Zvýrazněný kód](media/synctype_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přejmenování souboru *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde *Filename* je název aktuálního souboru.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **přejmenování souboru *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde  *Název souboru* je název aktuálního souboru.

   Typ nebo soubor okamžitě se přejmenuje.  V příkladu níže soubor **Employee.vb** byla přejmenována na **Person.vb** tak, aby odpovídaly název typu.

   ![Vložené výsledek](media/synctype_result.png)

## <a name="see-also"></a>Viz také  
[Refaktoringu (Visual Basic)](../refactoring-vb.md)
