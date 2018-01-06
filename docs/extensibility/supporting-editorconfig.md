---
title: "Rozšíření Služba jazyka pro podporu EditorConfig v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9b38601953fd5b1c80e5eeffd75c2fdc2608fc73
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="supporting-editorconfig-for-your-language-service"></a>Podpora EditorConfig služby jazyk

[EditorConfig](http://editorconfig.org/) soubory umožňují popisují běžné možnosti text editoru, jako je například velikost odsazení v jednotlivých projektů. Další informace o sadě Visual Studio podpora EditorConfig souborů najdete v tématu [vytvoření přenosné editor nastavení pomocí EditorConfig](../ide/create-portable-custom-editor-options.md).

Ve většině případů při implementaci služby jazykové sady Visual Studio, je žádné další kroky potřebné k podpoře EditorConfig universal vlastnosti. Editor základní automaticky vyhledá a načte soubor .editorconfig, když uživatelé otevřít soubory, a nastaví příslušná text možnosti vyrovnávací paměti a zobrazení. Pro úpravy, jako jsou karty a prostory, ale některé služby jazyk opt používá možnost zobrazení příslušné kontextové text namísto použití globální nastavení. V těchto případech služba jazyka musí být aktualizované kvůli podpoře EditorConfig soubory.

Toto jsou změny, které jsou potřeba k aktualizaci služby jazyk pro podporu EditorConfig soubory, tak, že nahradíte globální konfiguraci _konkrétní jazyk_ možnost s _kontextové_ možnost:

## <a name="indent-style"></a>Styl odsazení

Možnosti pro specifický jazyk | Kontextová možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|! textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>! textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>Velikost odsazení

Možnosti pro specifický jazyk | Kontextová možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>Velikost tabulátoru

Možnosti pro specifický jazyk | Kontextová možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>Viz také

[Vytvoření pomocí EditorConfig nastavení přenosné editoru](../ide/create-portable-custom-editor-options.md)  
[Rozšíření služby editoru a jazyk](../extensibility/extending-the-editor-and-language-services.md)