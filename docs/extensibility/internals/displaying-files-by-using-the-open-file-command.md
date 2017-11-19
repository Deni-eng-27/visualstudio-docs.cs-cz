---
title: "Zobrazení souborů pomocí příkaz pro otevření souboru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, supporting Open File command
- Open File command
- persistence, supporting Open File command
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f2cbcb6e6239552ae32c817601634587a2fe3a41
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="displaying-files-by-using-the-open-file-command"></a>Zobrazení souborů pomocí příkaz pro otevření souboru
Následující kroky popisují, jak rozhraní IDE zpracovává **otevření souboru** příkaz, který je k dispozici na **soubor** nabídky v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Kroky také popisují, jak mají projekty reagovat na volání, které pocházejí z tohoto příkazu.  
  
 Když uživatel klikne **otevření souboru** příkaz na **soubor** nabídce a vybere soubor z **otevření souboru** dialogové okno, se spustí následující proces.  
  
1.  Pomocí spuštěné tabulce dokumentu, rozhraní IDE zjistí, zda soubor je již otevřen v projektu.  
  
    -   Pokud je soubor otevřít, rozhraní IDE resurfaces okna.  
  
    -   Pokud soubor není otevřený, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> dotazovat každý projekt k určení, které projektu můžete otevřít soubor.  
  
        > [!NOTE]
        >  V implementaci projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, zadejte hodnotu priority, která informuje o úrovni, na které projektu otevře soubor. Hodnoty priority jsou součástí <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> výčtu.  
  
2.  Každý projekt, odpoví úroveň priority, který označuje význam se umístí na právě projekt k otevření souboru.  
  
3.  Prostředí IDE používá následující kritéria k určení, které projektu otevře soubor:  
  
    -   Projekt, který odpovídá s nejvyšší prioritou (DP_Intrinsic) otevře soubor. Pokud více než jeden projekt odpoví této priority, otevře se soubor první projekt reagovat.  
  
    -   Pokud žádné odpoví projektu s nejvyšší prioritou (DP_Intrinsic), ale všechny projekty odpověď s stejné, nižší prioritu, aktivní projekt se otevře soubor. Pokud je aktivní žádný projekt, první projekt reagovat otevře soubor.  
  
    -   Pokud žádný projekt deklarací vlastnictví souboru (DP_Unsupported), otevře se soubor různé soubory projektu.  
  
         Pokud je vytvořena instance různé soubory projektu, se s hodnotou DP_CanAddAsExternal vždy odpovídá projektu. Tato hodnota označuje, že projekt můžete otevřít soubor. Tento projekt se používá k levné otevřených souborů, které nejsou v jiných projektů. Seznam položek v tomto projektu není trvalý; Tento projekt je zobrazen v **Průzkumníku řešení** pouze pokud slouží k otevření souboru.  
  
         Pokud různé soubory projektu nevyplývá, aby mohli soubor otevřít, nebyla vytvořena instance projektu. V takovém případě rozhraní IDE vytvoří instanci různé soubory projektu a informuje projekt k otevření souboru.  
  
4.  Jakmile IDE určuje projekt, který otevře soubor, zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> metodu daného projektu.  
  
5.  Projekt pak nemá možnost otevření souboru pomocí editoru specifické pro projekt nebo standardního editoru. Další informace najdete v tématu [postup: Otevřete projekt konkrétní editory](../../extensibility/how-to-open-project-specific-editors.md) a [postup: otevřete standardní editory](../../extensibility/how-to-open-standard-editors.md), v uvedeném pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení souborů pomocí příkazu Open](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [Otevření a uložení položky projektu](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: otevření projektu konkrétní editory](../../extensibility/how-to-open-project-specific-editors.md)   
 [Postupy: otevření standardní editory](../../extensibility/how-to-open-standard-editors.md)