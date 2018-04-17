---
title: Správa zámku vlastníka dokumentu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document locking
ms.assetid: fa1ce513-eb7d-42bc-b6e8-cb2433d051d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65f5a38f5d4da0986b7f95c9287a94e657efa9c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="document-lock-holder-management"></a>Správa vlastníka zámku dokumentu
Spuštění dokumentu EFS (r... tabulky) zaznamenává počet otevřené dokumenty a zámky žádné úpravy, které mají. Zámek úpravy můžete umístit na dokument v r... při prostřednictvím kódu programu úpravách na pozadí bez uživatele zobrazuje dokument otevřít v okně dokumentu. Tato funkce se často používá návrháři, které upravují více souborů přes grafické uživatelské rozhraní.  
  
## <a name="document-lock-holder-scenarios"></a>Scénáře vlastníka zámku dokumentů  
  
### <a name="file-a-has-a-dependence-on-file-b"></a>Soubor "a" závislost na soubor má "b"  
 Představte si situaci, kdy implementovat standardního editoru "A" pro typ souboru "a" a každý soubor typu "a" obsahuje odkaz na (nebo závislost na) soubor typu "b". Pro soubory typu "b" existuje standardního editoru "B". Když se otevře editor "A" soubor "a" it načte odkaz na odpovídající soubor "b". Soubor "b" se nezobrazí, ale editor "A" ji upravit. Editor "A" získá odkaz na dokument data souboru "b" z <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> metoda a také udržuje zámek úpravy v souboru "b". Po dokončení editor "A" úpravy souboru "b" můžete snížení zámek upravit počet v souboru "b" voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> metoda. Tento krok můžete vynechat, pokud jste zavolal <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> metoda s parametrem `dwRDTLockType` nastavena na <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>.  
  
### <a name="file-b-is-opened-by-a-different-editor"></a>Jiný Editor je otevřít soubor "b"  
 V případě, že soubor "b" je již otevřen pomocí editoru "B", když se pokusí otevřít editor "A", existují dva samostatné scénáře pro zpracování:  
  
-   Pokud je v kompatibilní editoru otevřete soubor "b", musíte mít editor "A" zaregistrujte zámek úpravy dokumentu v souboru "b" pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> metoda. Po svém editoru "A" se provádí změny souboru "b", zrušení registrace dokumentu upravit pomocí zámku <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnregisterDocumentLockHolder%2A> metoda.  
  
-   Pokud je otevřen v nekompatibilním způsob soubor "b", můžete buď nechat pokus o otevření souboru "b" pomocí editoru "A" selhání, nebo můžete nechat zobrazit přidružené editor "A" částečně otevřete a zobrazí se příslušná chybová zpráva. Chybová zpráva by měla předat uživateli pokyny, zavřete soubor "b" v nekompatibilním editoru a pak znovu otevřete soubor "a" pomocí editoru "A". Můžete taky implementovat [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] metoda <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable2.QueryCloseRunningDocument%2A> uživatele zavřete soubor "b", který je otevřen v nekompatibilním editoru. Pokud uživatel nezavře souboru "b", otevření souboru "a" v editoru "A" pokračuje normálním způsobem.  
  
## <a name="additional-document-edit-lock-considerations"></a>Aspekty zámku upravit další dokumentu  
 Chcete získat různé chování v editoru "A" je pouze editor, který má dokument upravit zámku na soubor "b", než by pokud editor "B" také obsahuje dokument upravit zámku na soubor "b". V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **návrhář tříd** je příkladem vizuálního návrháře, který neobsahuje zámek úpravy v souboru přidružený kód. To znamená pokud má uživatel diagramu tříd, otevřete v zobrazení návrhu a současně otevřít soubor přidružený kód, a pokud uživatel změní souboru kódu, ale není uložit změny, změny jsou také ke ztrátě do souboru třídy diagram (.cd). Pokud **návrhář tříd** má pouze dokument upravit zámku v souboru kódu, uživatel není požádán o uložit změny při zavírání souboru kódu. Prostředí IDE uživateli výzvu k uložení změn až poté, co uživatel nezavře **návrhář tříd**. Uložené změny se projeví v oba soubory. Pokud **návrhář tříd** a editoru kódu souboru zámky úpravy dokumentu uložené v souboru kódu, pak bude uživatel vyzván k uložení při zavírání souboru kódu nebo formuláře. V tomto bodě uložené změny se projeví ve formuláři a souboru kódu. Další informace o diagramů tříd naleznete v tématu [práce s diagramy tříd (návrhář tříd)](../ide/working-with-class-diagrams-class-designer.md).  
  
 Všimněte si, že pokud je nutné umístit zámek úpravy dokumentu pro jiný editor, je nutné implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> rozhraní.  
  
 Kolikrát uživatelského rozhraní návrháře která upraví soubory kódu prostřednictvím kódu programu provede změny více než jeden soubor. V takových případech <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell2.SaveItemsViaDlg%2A> metoda zpracovává ukládání jeden nebo více dokumentů prostřednictvím **chcete uložit změny do následující položky?** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Spuštěné tabulce dokumentu](../extensibility/internals/running-document-table.md)   
 [Trvalost a spuštěná tabulka dokumentů](../extensibility/internals/persistence-and-the-running-document-table.md)