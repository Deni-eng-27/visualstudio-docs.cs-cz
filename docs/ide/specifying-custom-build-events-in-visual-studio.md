---
title: Určení vlastních událostí sestavení v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68068a88744484e0f9d1849a430a32fd3f4c1899
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="specifying-custom-build-events-in-visual-studio"></a>Specifikace vlastních událostí sestavení v sadě Visual Studio
Určení událostí sestavení vlastní, můžete automaticky spouštět příkazy před zahájením sestavení nebo po jejím dokončení. Můžete například spustit soubor .bat před sestavení spustí nebo zkopírujte nové soubory do složky, po dokončení sestavení. Události sestavení spustit pouze v případě, že sestavení úspěšně dosáhne těchto bodů v procesu sestavení.  
  
 Konkrétní informace o programovací jazyk, který používáte najdete v následujících tématech:  
  
-   Visual Basic –[postupy: určení událostí sestavení (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).  
  
-   C# a F # –[postupy: určení událostí sestavení (C#)](../ide/how-to-specify-build-events-csharp.md).  
  
-   Visual C++ –[zadání události sestavení](/cpp/ide/specifying-build-events).  
  
## <a name="syntax"></a>Syntaxe  
 Události sestavení použijte stejnou syntaxi jako DOS příkazy, ale makra můžete snadno vytvořit událostí sestavení. Seznam dostupných makra najdete v tématu [před sestavením událostí/po sestavení příkazového řádku dialogové okno události](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
 Nejlepších výsledků dosáhnete postupujte podle těchto tipy formátování:  
  
-   Přidat `call` spustit příkaz před všechny události sestavení, soubory .bat.  
  
     Příklad: `call C:\MyFile.bat`  
  
     Příklad: `call C:\MyFile.bat call C:\MyFile2.bat`  
  
-   Cesty k souborům uzavřete do uvozovek.  
  
     Příklad (pro [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "% ProgramFiles (x86) %\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe"-Pokud "$(TargetPath)"  
  
-   Oddělte více příkazů konce řádků.  
  
-   Podle potřeby použít zástupné znaky.  
  
     Příklad: `for %I in (*.txt *.doc *.html) do copy %I c:\` *mydirectory*`\`  
  
    > [!NOTE]
    >  `%I` ve výše uvedeném kódu by měla být `%%I` v dávkovém skriptu.  
  
## <a name="see-also"></a>Viz také  
 [Kompilaci a sestavování](../ide/compiling-and-building-in-visual-studio.md)   
 [Dialogové okno Příkazový řádek události/po sestavení události před sestavením](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [Speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md)   
 [Návod: Sestavení aplikace](../ide/walkthrough-building-an-application.md)