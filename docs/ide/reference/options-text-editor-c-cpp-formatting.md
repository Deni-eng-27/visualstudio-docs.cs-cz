---
title: Možnosti, textový editor, C/C++, formátování
ms.date: 04/30/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.C%2fC%2b%2b.Formatting.General
dev_langs:
- CPP
helpviewer_keywords:
- Text Editor Options dialog box, formatting
- ClangFormat
ms.assetid: cb6f1cbb-5305-48da-a8e8-33fd70775d46
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa4c543d19c43bd397d7d18a185a73a4bf161a6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53960745"
---
# <a name="options-text-editor-cc-formatting"></a>Možnosti, textový editor, C/C++, formátování

Chcete-li změnit výchozí chování editoru kódu při programování v jazyce C nebo C++, použijte tyto stránky vlastností.

[C++ formátování stránky vlastností](media/cpp-formatting.png)

 Pro přístup k této stránce v **možnosti** dialogové okno, v levém podokně rozbalte **textový Editor**, rozbalte **C/C++** a potom klikněte na tlačítko **formátování** .

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="general-page"></a>Obecná stránka

Tato stránka obsahuje možnosti formátování příkazů a bloků, jako je typu.

**Visual Studio 2017 verze 15.7 nebo novější**: Stránka také obsahuje možnosti pro konfiguraci podpory pro [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html) verze 5.0. ClangFormat je nástroj, který umožňuje snadno vytvořit styl a formátování kódu na základě sady pravidel, která se dá nakonfigurovat v souboru .clang-format nebo _clang-format.

### <a name="configuring-clangformat-options"></a>Konfigurace možností ClangFormat

V sadě Visual Studio 2017 verze 15.7 nebo novější je standardně povolená podporu pro ClangFormat. Můžete vybrat, které tyto běžné konvence formátování se mají použít na všechny projekty: Kompilátor LLVM, Google, chromu, Mozilla nebo komponenty WebKit. Můžete také vytvořit definici vlastního formátu souboru .clang-format nebo _clang-format. Pokud se tento soubor nachází ve složce projektu, Visual Studio používá k formátování všechny soubory zdrojového kódu v této složce a jejích podsložkách. 

Ve výchozím nastavení sady Visual Studio clangformat.exe běží na pozadí použije formátování při psaní. Můžete také zadat pouze pro ji spustit ručně vyvolat příkazy formátování **formátovat dokument (Ctrl + K, Ctrl + D)** nebo **formátovat výběr (Ctrl + K, Ctrl + F)**.


## <a name="indentation-new-lines-spacing-wrapping-pages"></a>Odsazení, nové řádky mezery obtékání stránky

Tyto stránky umožňují provádět přizpůsobení různých formátování, ale jsou ignorovány, pokud je povolené ClangFormat.

## <a name="see-also"></a>Viz také

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Používání atributu IntelliSense](../../ide/using-intellisense.md)