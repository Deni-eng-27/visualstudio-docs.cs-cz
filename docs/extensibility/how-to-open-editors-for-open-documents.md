---
title: 'Postupy: Otevření editorů pro otevřené dokumenty | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 654fdb6a921a0d6a25490b17f6f0ce3ffafa4ae4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62863126"
---
# <a name="how-to-open-editors-for-open-documents"></a>Postupy: Otevření editorů pro otevřené dokumenty
Předtím, než projekt se otevře okno dokumentu, projekt nejprve musíte určit, zda soubor je již otevřen, v okně dokumentu pro jiný editor. Soubor může být buď otevřít v editoru specifické pro projekt nebo jeden standardní Editor zaregistrovaný s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="open-a-project-specific-editor"></a>Otevřete editor specifické pro projekt
 Pomocí následujícího postupu otevřete editor specifické pro projekt pro soubor, který je již otevřen.

### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>Chcete-li otevřít editor specifické pro projekt pro otevření souboru

1. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> metody.

    Toto volání vrátí ukazatele do hierarchie, položku hierarchie a okna rámce dokumentu v případě potřeby.

2. Pokud je otevřít dokument, projekt musí zkontrolujte, zda existuje pouze datový objekt dokumentu, nebo objekt zobrazení dokumentu je také k dispozici.

   - Pokud existuje objekt zobrazení dokumentu a toto zobrazení je pro jiné hierarchie nebo hierarchie položek, projekt používá ukazatel na rámec okna v zobrazení pro resurface existující okno.

   - Pokud existuje objekt zobrazení dokumentu a toto zobrazení je na stejné hierarchie a hierarchie položek, můžete projekt otevřít druhého zobrazení Pokud můžete připojit k podkladový datový objekt dokumentu. V opačném případě projektu používejte ukazatel na rámec okna v zobrazení pro resurface existující okno.

   - Pokud dokument datový objekt existuje, jenom projektu by měl určit, zda datový objekt dokumentu může použít pro jeho zobrazení. Pokud je datový objekt dokumentu kompatibilní, dokončení kroků popsaných v [otevřete editor specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).

     Pokud datový objekt dokumentu není kompatibilní, by měl uživateli, který označuje, že soubor je aktuálně používán zobrazí chyba. Tato chyba má být zobrazen v občasné případy, pouze, například když je kompilován soubor v době, uživatel se pokusil otevřít soubor pomocí editoru jiné než [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] core textového editoru. Základní text editor můžete sdílet s kompilátor dokumentu datový objekt.

3. Pokud dokument není otevřen, protože neexistuje žádný dokument datového objektu nebo objekt zobrazení dokumentu, proveďte kroky v [otevřete editor specifické pro projekt](../extensibility/how-to-open-project-specific-editors.md).

## <a name="open-a-standard-editor"></a>Otevřete standardní editor
 Pomocí následujícího postupu otevřete standardní editor pro soubor, který už je otevřít.

### <a name="to-open-a-standard-editor-for-an-open-file"></a>Chcete-li otevřít standardní editor pro otevření souboru

1. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.

     Tato metoda nejprve ověří, že dokument ještě není otevřené voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>. Pokud už je dokument otevřete, pak resurfaced jeho okno editoru.

2. Pokud dokument není otevřen, potom postupujte podle pokynů v [jak: Otevření standardních editorů](../extensibility/how-to-open-standard-editors.md).

## <a name="see-also"></a>Viz také:
- [Otevření a uložení položek projektu](../extensibility/internals/opening-and-saving-project-items.md)
- [Postupy: Otevřít editoru pro konkrétní projekt](../extensibility/how-to-open-project-specific-editors.md)
- [Postupy: Otevřít standardních editorů](../extensibility/how-to-open-standard-editors.md)
