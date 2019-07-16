---
title: Vytvoření instance základní Editor pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - instantiating editor
ms.assetid: dda23b18-96ef-43c6-b0dc-06d15cbe5cbb
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 29306a16390039c8ee6e424b81a5ff617e533ab4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203912"
---
# <a name="instantiating-the-core-editor-by-using-the-legacy-api"></a>Vytvoření instance základního editoru pomocí zastaralého rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editor je zodpovědná za funkce jako je například vložení, odstranění, zkopírování a vložení pro úpravy textu. Je kombinací těchto funkcí s těmi, která poskytuje služby jazyka, jako je text barvy, odsazení a dokončování příkazů IntelliSense.  
  
 Můžete vytvořit instanci instance základní editor v jednom ze tří způsobů:  
  
- Explicitní vytvoření instance základní editoru v okně.  
  
- Zadejte objekt factory editoru, který vrátí instance základní editor  
  
- Otevřete soubor z hierarchie projektu.  
  
  Následující části popisují, jak vytvořit instanci editoru pomocí starší verze rozhraní API.  
  
## <a name="explicitly-opening-a-core-editor-instance"></a>Explicitně otevírání instanci základním editoru  
 Při získávání explicitně instance základní editor:  
  
- Získání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> pro uchování objektu data dokumentu, který právě upravujete.  
  
- Vytvořit řádek orientovaný reprezentace datového objektu dokumentu vytvořením <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní.  
  
- Nastavte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> jako datový objekt dokumentu pro instanci výchozí implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> rozhraní, pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetBuffer%2A> metody.  
  
   Hostitele <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> instance v <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> rozhraní pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateToolWindow%2A> metoda.  
  
  V tomto okamžiku zobrazení <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> poskytuje rozhraní představující instanci základní editor.  
  
  Ale to není velmi užitečné instance, protože ho neobsahuje klávesové zkratky, nebo přístup k pokročilým funkcím. Chcete-li získat přístup k klávesové zkratky a další funkce:  
  
- Použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metoda, jak přidružit služba jazyka a datový objekt dokumentu, který používá editoru.  
  
- Vytvořit vlastní klávesové zkratky, nebo použít výchozí systémové hodnoty tak, že nastavíte <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekty zobrazení vlastností. Chcete-li to provést, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetGuidProperty%2A> metodou <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> vlastnost.  
  
   Chcete-li získat a používat nestandardní klávesové zkratky, vygenerujte pomocí souboru .vsct. Další informace najdete v tématu [tabulky příkazů aplikace Visual Studio (. Vsct) soubory](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="how-to-use-an-editor-factory-to-obtain-the-core-editor"></a>Způsob použití objektu pro vytváření editoru získat základní Editor  
 Při implementaci základní editor se objekt pro vytváření editoru pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metodu, postupujte podle všech kroků uvedených v předchozí části explicitně hostovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> data dokumentu v objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objektu.  
  
 Chcete-li zobrazit text, získat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> objektu a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody.  
  
 K zajištění služeb jazyka do editoru, zavolejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metody v rámci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda.  
  
 Získat výchozí klávesové zkratky, na rozdíl od předchozí části, použijte příkaz kontextu vrácené <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda při získávání základní editor z <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody.  
  
 Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda vrátí identifikátor GUID stejný příkaz jako textový editor, instance základní editor automaticky získá výchozí klávesové zkratky.  
  
 Obecné informace najdete v tématu [názorný postup: Základní Editor vytváří a registruje typem souboru Editor](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md).  
  
## <a name="see-also"></a>Viz také  
 [Uvnitř základní Editor](../extensibility/inside-the-core-editor.md)   
 [Otevření a uložení položek projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Návod: Vytvoření základního editoru a registrace typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)
