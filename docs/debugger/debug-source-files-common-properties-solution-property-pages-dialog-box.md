---
title: Ladit zdrojové soubory/společné vlastnosti/stránky vlastností řešení
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 735432db485277e2265479e625f5e8acaa2cc2e3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72738402"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Ladění zdrojových souborů, společná nastavení, dialogové okno stránek vlastností řešení
Tato stránka vlastností určuje, kde bude ladicí program při ladění řešení hledat zdrojové soubory.

 Chcete-li získat přístup ke stránce vlastností **zdrojové soubory ladění** , klikněte pravým tlačítkem myši na řešení v **Průzkumník řešení** a v místní nabídce vyberte možnost **vlastnosti** . Rozbalte složku **Společná nastavení** a klikněte na stránku **zdrojové soubory ladění** .

 **Adresáře obsahující zdrojový kód** Obsahuje seznam adresářů, ve kterých ladicí program vyhledává zdrojové soubory při ladění řešení. Prohledají se také podadresáře určených adresářů.

 **Nehledat tyto zdrojové soubory** Zadejte názvy všech souborů, které nechcete, aby ladicí program četl. Pokud ladicí program nalezne jeden z těchto souborů v jednom z výše uvedených adresářů, bude ho ignorovat. Pokud se dialogové okno **Najít zdroj** objeví během ladění a, kliknete na **Zrušit**, soubor, který jste hledali, se přidá do tohoto seznamu, aby ladicí program nepokračoval v hledání tohoto souboru.

## <a name="see-also"></a>Viz také

- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)