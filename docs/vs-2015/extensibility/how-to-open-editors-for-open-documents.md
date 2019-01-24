---
title: 'Postupy: Otevření editorů pro otevřené dokumenty | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1a8238ce632f8552b36ccb259af683636732b469
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788749"
---
# <a name="how-to-open-editors-for-open-documents"></a>Postupy: Otevření editorů pro otevřené dokumenty
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Předtím, než projekt se otevře okno dokumentu, projekt nejprve musíte určit, zda soubor je již otevřen, v okně dokumentu pro jiný editor. Soubor může být buď otevřít v editoru specifické pro projekt nebo jeden standardní Editor zaregistrovaný s [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="opening-a-project-specific-editor"></a>Otevření editoru specifické pro projekt  
 Pomocí následujícího postupu otevřete editor specifické pro projekt pro soubor, který je již otevřen.  
  
#### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>Chcete-li otevřít editor specifické pro projekt pro otevření souboru  
  
1. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> metody.  
  
    Toto volání vrátí ukazatele do hierarchie, položku hierarchie a okna rámce dokumentu v případě potřeby.  
  
2. Pokud je otevřít dokument, projekt musí zkontrolujte, zda existuje pouze datový objekt dokumentu, nebo objekt zobrazení dokumentu je také k dispozici.  
  
   - Pokud existuje objekt zobrazení dokumentu a toto zobrazení je pro jiné hierarchie nebo hierarchie položek, projekt používá ukazatel na rámec okna v zobrazení pro resurface existující okno.  
  
   - Pokud existuje objekt zobrazení dokumentu a toto zobrazení je na stejné hierarchie a hierarchie položek, můžete projekt otevřít druhého zobrazení Pokud můžete připojit k podkladový datový objekt dokumentu. V opačném případě projektu používejte ukazatel na rámec okna v zobrazení pro resurface existující okno.  
  
   - Pokud dokument datový objekt existuje, jenom projektu by měl určit, zda datový objekt dokumentu může použít pro jeho zobrazení. Pokud je datový objekt dokumentu kompatibilní, dokončení kroků popsaných v [otevření editoru specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).  
  
     Pokud datový objekt dokumentu není kompatibilní, by měl uživateli, který označuje, že soubor je aktuálně používán zobrazí chyba. Tato chyba má být zobrazen v občasné případy, pouze, například když je kompilován soubor v době, uživatel se pokusil otevřít soubor pomocí editoru jiné než [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] core textového editoru. Základní text editor můžete sdílet s kompilátor dokumentu datový objekt.  
  
3. Pokud dokument není otevřen, protože neexistuje žádný dokument datového objektu nebo objekt zobrazení dokumentu, proveďte kroky v [otevření editoru specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).  
  
## <a name="opening-a-standard-editor"></a>Otevření editoru Standard  
 Pomocí následujícího postupu otevřete standardní editor pro soubor, který už je otevřít.  
  
#### <a name="to-open-a-standard-editor-for-an-open-file"></a>Chcete-li otevřít standardní editor pro otevření souboru  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
     Tato metoda nejprve ověří, že dokument ještě není otevřené voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>. Pokud už je dokument otevřete, pak resurfaced jeho okno editoru.  
  
2.  Pokud dokument není otevřen, potom postupujte podle pokynů v [jak: Otevření standardních editorů](../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Viz také  
 [Otevření a uložení položek projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: Otevřít editoru pro konkrétní projekt](../extensibility/how-to-open-project-specific-editors.md)   
 [Postupy: Otevřít standardních editorů](../extensibility/how-to-open-standard-editors.md)
