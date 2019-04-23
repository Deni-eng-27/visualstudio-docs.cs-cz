---
title: Uložení vlastního dokumentu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- persistence, saving custom documents
- projects [Visual Studio SDK], saving custom documents
- editors [Visual Studio SDK], saving custom documents
ms.assetid: 040b36d6-1f0a-4579-971c-40fbb46ade1d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f32f710b6e9749628716181ecf309f2520be041d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60078262"
---
# <a name="saving-a-custom-document"></a>Uložení vlastního dokumentu
Obslužné rutiny prostředí **Uložit**, **uložit jako**, a **Uložit vše** příkazy. Když uživatel klikne **Uložit**, **uložit jako**, **nebo Uložit vše** na **souboru** nabídky nebo zavření řešení, což vede k Uložit vše, následující proces se provádí.

 ![Editor zákazníka Uložit](../../extensibility/internals/media/private.gif "privátní") uložit, uložit jako a Uložit vše zpracování příkazů pro vlastní editor

 Tento proces je podrobně popsán v následujících krocích:

1. Pro **Uložit** a **uložit jako** příkazy, používá prostředí <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby k určení aktivního okna dokumentu, a proto položky by měly být uloženy. Jakmile okno aktivního dokumentu je známé, vyhledá prostředí hierarchie ukazatele a identifikátor položky (itemID) dokumentu v tabulce spuštěných dokumentů. Další informace najdete v tématu [spuštěná tabulka dokumentů](../../extensibility/internals/running-document-table.md).

     Pro příkaz Uložit vše prostředí používá informace v tabulce spuštěných dokumentů pro kompilaci seznam všech položek na Uložit.

2. Když řešení obdrží <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> volání, prochází sadu vybraných položek (to znamená více výběrů, které jsou vystavené <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> služby).

3. Pro každou položku do výběru, toto řešení využívá ukazatel hierarchie volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> metodou ke zjištění, zda má být povolen příkaz nabídky Uložit. Pokud jeden nebo více položek jsou chybná, je povoleno příkazu Uložit. Pokud v hierarchii používá standardní editor, pak dotazování na hierarchii delegáty nesprávné stav do editoru voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> metody.

4. Pro každou vybranou položku není čistá, toto řešení využívá ukazatel hierarchie volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> metodu na odpovídající hierarchie.

     V případě vlastní editor komunikace mezi datový objekt dokumentu a projekt je privátní. Proto jakékoli obavy speciální stálost jsou zpracovány mezi těmito dvěma objekty.

    > [!NOTE]
    >  Pokud se rozhodnete implementovat vlastní trvalost, nezapomeňte volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> metoda šetří čas. Tato metoda zkontroluje, aby se zajistilo, že se můžete bezpečně uložit soubor (například soubor není jen pro čtení).

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>
- [Otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md)