---
title: Zobrazení souborů pomocí příkazu otevřít v programu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4051793077e613981e1dd5b44f1736878f5853e9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80708583"
---
# <a name="display-files-by-using-the-open-with-command"></a>Zobrazení souborů pomocí příkazu otevřít v programu
Projekt může požádat IDE o zobrazení dialogového okna **otevřít v programu** . Tento požadavek vyzve uživatele k otevření souboru, který má výběr standardních editorů. Tento proces je popsán v následujících krocích:

1. Projekt volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> zadání hodnoty `OSE_UseOpenWithDialog` `OSEOpenDocEditor` parametru.

2. V závislosti na příponě názvu souboru v dokumentu rozhraní IDE určí, které editory uvedené v registru můžou otevřít zadaný dokument a zobrazit tyto informace v dialogovém okně **otevřít v programu** .

    > [!NOTE]
    > Projekty, které mají vnitřní editor, který musí být zahrnut v dialogovém okně **otevřít v programu** , musí zaregistrovat objekt pro vytváření editoru pro každý takový editor. Vnitřní editory fungují pouze v rámci konkrétního typu projektu, který je vynutil při implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody. Rozhraní IDE má vestavěný objekt pro vytváření editoru pro základní textový editor a binární editor. Rozhraní IDE také vytvoří instanci objektu pro vytváření editoru jménem každého zaregistrovaného přidružení souborů systému Windows. Příkladem takového souboru je Microsoft Word.

3. Jakmile uživatel vybere položku v dialogovém okně **otevřít v programu** , rozhraní IDE pak otevře dokument voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metody. Další informace najdete v tématu [Postup: otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md).

## <a name="see-also"></a>Viz také
- [Otevřít a uložit položky projektu](../../extensibility/internals/opening-and-saving-project-items.md)
- [Zobrazení souborů pomocí příkazu otevřít soubor](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)
- [Postupy: otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md)
