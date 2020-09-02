---
title: Podrobnosti o konfiguraci správy zdrojového kódu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], configuration details
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5faa0ce575647038ac5ac7839b6dc066b7b51ce6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "64822041"
---
# <a name="source-control-configuration-details"></a>Podrobnosti konfigurace správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Aby bylo možné implementovat správu zdrojového kódu, je nutné správně nakonfigurovat systém projektu nebo editor, aby bylo možné provést následující akce:  
  
- Požádat o oprávnění k přechodu na změněný stav  
  
- Požádat o oprávnění k uložení souboru  
  
- Požádat o oprávnění k přidání, odebrání nebo přejmenování souborů v projektu  
  
## <a name="request-permission-to-transition-to-changed-state"></a>Požádat o oprávnění k přechodu na změněný stav  
 Projekt nebo editor musí požádat o oprávnění k přechodu do změněného (nečistého) stavu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> . Každý editor, který implementuje, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> musí volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> a přijmout schválení pro změnu dokumentu z prostředí před vrácením `True` `M:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty(System.Int32@)` . Projekt je v podstatě editor pro soubor projektu a výsledkem je stejná zodpovědnost za implementaci sledování změny stavu projektu jako textový editor pro jeho soubory. Prostředí zpracovává změněný stav řešení, ale je nutné zpracovat změněný stav libovolného objektu, který řešení odkazuje, ale neukládá, jako soubor projektu nebo jeho položky. Obecně platí, že pokud je váš projekt nebo editor zodpovědný za správu trvalosti položky, zodpovídá za implementaci sledování stavu změny.  
  
 V reakci na `IVsQueryEditQuerySave2::QueryEditFiles` volání může prostředí provádět následující akce:  
  
- Zamítnout volání ke změně. v takovém případě musí Editor nebo projekt zůstat ve stavu Unchanged (Clean).  
  
- Označuje, že se data dokumentu mají znovu načíst. V případě projektu prostředí znovu nasadí data projektu. Editor musí znovu načíst data z disku prostřednictvím jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> implementace. V obou případech se kontext v projektu nebo editoru může změnit, když jsou data znovu načtena.  
  
  Je to složitá a obtížná úloha pro zpětnému pozměněníí odpovídajících `IVsQueryEditQuerySave2::QueryEditFiles` volání do stávající základny kódu. V důsledku toho by tato volání měla být integrována během vytváření projektu nebo editoru.  
  
## <a name="request-permission-to-save-a-file"></a>Požádat o oprávnění k uložení souboru  
 Před tím, než projekt nebo editor uloží soubor, musí zavolat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> . Pro soubory projektu jsou tato volání automaticky dokončena řešením, které ví, kdy uložit soubor projektu. Editory jsou zodpovědné za provedení těchto volání, pokud Editor implementuje `IVsPersistDocData2` použití pomocné funkce <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> . Pokud editor `IVsPersistDocData2` tímto způsobem implementuje, pak volání `IVsQueryEditQuerySave2::QuerySaveFile` nebo `IVsQueryEditQuerySave2::QuerySaveFiles` je provedeno za vás.  
  
> [!NOTE]
> Tyto výzvy vždy provedete bez přerušení – tedy v době, kdy je váš Editor schopný přijmout zrušení.  
  
## <a name="request-permission-to-add-remove-or-rename-files-in-the-project"></a>Požádat o oprávnění k přidání, odebrání nebo přejmenování souborů v projektu  
 Předtím, než projekt může přidat, přejmenovat nebo odebrat soubor nebo adresář, musí zavolat odpovídající `IVsTrackProjectDocuments2::OnQuery*` metodu pro vyžádání oprávnění z prostředí. Pokud je uděleno oprávnění, projekt musí dokončit operaci a pak zavolat odpovídající `IVsTrackProjectDocuments2::OnAfter*` metodu pro informování prostředí, že operace byla dokončena. Projekt musí volat metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> rozhraní pro všechny soubory (například speciální soubory) a ne pouze nadřazené soubory. Volání souborů jsou povinná, ale volání adresáře jsou volitelná. Pokud má váš projekt informace o adresáři, pak by měl volat vhodné <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> metody, ale pokud tyto informace neobsahuje, bude prostředí odvodit informace o adresáři.  
  
 Projekt by neměl volat metody `IVsTrackProjectDocuments2` při otevření nebo zavření projektu. Naslouchací procesy, které chtějí tyto informace při spuštění, můžou počkat na <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> událost a iterovat v rámci řešení, aby našli informace, které potřebují. Při vypnutí se tyto informace nevyžadují. `IVsTrackProjectDocuments2` je k dispozici z <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> .  
  
 Pro každou akci přidání, přejmenování a odebrání je k dispozici `OnQuery*` Metoda a `OnAfter*` metoda. Zavolejte `OnQuery*` metodu pro vyžádání oprávnění k přidání, přejmenování nebo odebrání souboru nebo adresáře. Volejte `OnAfter*` metodu po přidání, přejmenování nebo odebrání souboru nebo adresáře a stav projektu odpovídá novému stavu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>   
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)
