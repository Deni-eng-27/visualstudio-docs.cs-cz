---
title: "Dialogové okno Možnosti, projekty a řešení, sestavit a spustit | Microsoft Docs"
ms.custom: 
ms.date: 07/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0187b8a70fc012fc6d2564f77ea5a2b2ff7c20d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>Dialogové okno Možnosti, projekty a řešení, sestavit a spustit

V tomto dialogovém můžete zadat maximální počet projekty Visual C++ a Visual C#, které můžete vytvořit ve stejnou dobu, sestavení určité výchozí chování a některé sestavení nastavení protokolu. Chcete-li získat přístup k tyto možnosti, vyberte **nástroje > Možnosti** rozbalte **projekty a řešení**a vyberte **sestavit a spustit**.
  
**Maximální počet paralelní projektu sestavení**  
Určuje maximální počet projekty Visual C++ a Visual C#, které můžete vytvořit ve stejnou dobu. K optimalizaci procesu sestavení, se automaticky nastaví maximální počet paralelní projektu sestavení na počet procesorů v počítači. Maximální počet je 32.  

**Pouze při spuštění sestavení projektů po spuštění a závislosti**  
Při použití klíče, vyberte F5 sestavení spouštěný projekt a jeho závislé součásti **ladění > Spustit** příkaz nabídky, nebo použít příkazy na **sestavení** nabídky. Pokud je prázdné, jsou všechny projekty a závislosti sestavení. 

**Při spuštění, když jsou zastaralé projekty**  
*Platí pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] pouze projekty.*

Při spuštění projektu pomocí F5 nebo **ladění > Spustit** příkaz, ve výchozím nastavení **výzva k vytvoření** zobrazí zprávu, pokud není aktuální konfigurací projektu. Vyberte **vždy sestavení** a tím projekt sestavit pokaždé, když je spuštěná. Vyberte **nikdy sestavení** při spuštění projektu potlačit všechny automatické sestavení.

**Při spuštění, když sestavení nebo dojít k chybám nasazení**  
*Platí pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] pouze projekty.*

Při spuštění projektu pomocí F5 nebo **ladění > Spustit** příkaz, ve výchozím nastavení **výzva ke spuštění** zobrazí zprávu, pokud projekt by měl být spuštěn i v případě, že sestavení se nezdařilo. Vyberte **stará verze spuštění** a automaticky spustit poslední dobrý sestavení, což by mohlo vést neshody mezi spuštěním kódu a zdrojový kód. Vyberte **nespouštějí** k potlačení zprávy.

**Pro nové řešení použít aktuálně vybraný projekt jako spouštěný projekt**  
Pokud je tato možnost nastavená, použijte nové řešení aktuálně vybrané projekt jako spouštěný projekt.  

**Podrobnosti výstup sestavení projektu MSBuild**  
Určuje, kolik informací se zobrazí v **výstup** okna pro sestavení.  

**Podrobnosti souboru MSBuild projektu sestavení protokolu**  
*Platí pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] pouze projekty.*

Určuje, kolik informací je zapsán do souboru protokolu sestavení, která se nachází v \\... \\ *ProjectName*\Debug\\*ProjectName*. log.  

## <a name="see-also"></a>Viz také  
[Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)  
[Dialogové okno Možnosti, projekty a řešení](projects-and-solutions-options-dialog-box.md)  
[Dialogové okno Možnosti, projekty a řešení, webové projekty](options-dialog-box-projects-and-solutions-web-projects.md)