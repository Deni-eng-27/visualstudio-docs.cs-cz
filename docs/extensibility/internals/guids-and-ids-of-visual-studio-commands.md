---
title: Identifikátory GUID a ID příkazů sady Visual Studio | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: daf131fd6d7940458252e734ab0cc222f2e3a357
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62860963"
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>Příkazy identifikátory GUID a ID sady Visual Studio
Hodnoty GUID a ID příkazů součástí integrovaného vývojového prostředí (IDE) sady Visual Studio jsou definovány v souborech .vsct, které se instalují jako součást sady Visual Studio SDK. Další informace najdete v tématu [příkazy definované prostředím IDE, nabídky a skupiny](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).

 Další informace o tom, jak pracovat s objekty integrovaného vývojového prostředí, které jsou definovány v *.vsct* soubory, naleznete v tématu [rozšířit nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).

## <a name="find-a-command-definition"></a>Vyhledání definice příkazu
 Visual Studio definuje více než 1 000 příkazy, proto je nepraktické uvádět na seznamu všechny zde. Místo toho použijte následující postup najděte definici příkazu.

### <a name="to-locate-a-command-definition"></a>Vyhledejte definici příkazu

1. V sadě Visual Studio, otevřete následující soubory v seznamu *< cesta instalace sady Visual Studio SDK\>\VisualStudioIntegration\Common\Inc\\*  složky: *SharedCmdDef.vsct*, *ShellCmdDef.vsct*, *VsDbgCmdUsed.vsct*, *Venusmenu.vsct*.

    Většina příkazů sady Visual Studio jsou definovány v *SharedCmdDef.vsct* a *ShellCmdDef.vsct*. *VsDbgCmdUsed.vsct* definuje příkazy, které se vztahují k ladicímu programu, a *Venusmenu.vsct* definuje příkazy, které jsou specifické pro vývoj pro Web.

2. Pokud je příkaz položku nabídky, mějte na paměti přesný text položky nabídky. Pokud je příkaz tlačítka na panelu nástrojů, mějte na paměti text popisku, který se zobrazí při pozastavení na něj.

3. Stisknutím klávesy **Ctrl**+**F** otevřít **najít** dialogové okno.

4. V **najít** zadejte text, který jste si poznamenali v kroku 2.

5. Ověřte, že **všechny otevřené dokumenty** se zobrazí **Hledat v** pole.

6. Klikněte na tlačítko **najít další** tlačítko opakovaným text `<Strings>` část [element přepínače](../../extensibility/button-element.md).

    `<Button>` Element, který se zobrazí v příkazu je příkaz definice.

   Po nalezení definici příkazu můžete umístit kopii tohoto příkazu na jinou nabídku nebo panel nástrojů tak, že vytvoříte [commandplacement – element](../../extensibility/commandplacement-element.md) , který má stejný `guid` a `id` hodnoty jako u příkazu. Další informace najdete v tématu [vytváření znovu použitelných skupin tlačítek](../../extensibility/creating-reusable-groups-of-buttons.md).

### <a name="special-cases"></a>Zvláštní případy
 V následujících případech text nabídky nebo text popisku nemusí přesně odpovídat co je v definici příkazu.

- Položky nabídky, které obsahují podrženého znaku, například **tisk** příkaz **souboru** nabídka, ve kterém *P* podtržené.

     Znaky, které předchází znak ampersand (&) znaků v názvech položek nabídky se zobrazí jako podtržené. Ale *.vsct* soubory jsou zapsány ve formátu XML, který používá znak ampersand (&) k označení speciální znaky a vyžaduje, že musí být zadán znak ampersand, který se má zobrazit jako  *&amp;amp;*. Proto v *.vsct* souboru **tisk** příkazu se zobrazí jako  *&amp;amp; Tisk*.

- Příkazy, které mají dynamický text, například **Uložit** \<aktuální Filename\>a dynamicky generované položky nabídky, jako je například položky na **poslední soubory** seznamu.

     Neexistuje žádný spolehlivý způsob pro vyhledávání na dynamický text. Místo toho najít skupinu, který je hostitelem požadovaného příkazu v součinnosti s [identifikátory GUID a ID sady Visual Studio nabídky](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) nebo [identifikátory GUID a ID sady Visual Studio panely nástrojů](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)a vyhledat ID této skupiny. Pokud definice příkazu nemá žádné skupiny jako jeho [nadřazeného elementu](../../extensibility/parent-element.md), hledání *SharedCmdPlace.vsct* a *ShellCmdPlace.vsct* (nebo  *VsDbgCmdPlace.vsct* pro příkazy ladicího programu) pro `<CommandPlacement>` element, který nastaví nadřazeného tohoto příkazu. *SharedCmdPlace.vsct*, *ShellCmdPlace.vsct*, a *VsDbgCmdPlace.vsct* v *\<cestu instalace sady Visual Studio SDK\>\ VisualStudioIntegration\Common\Inc\\* složky.

## <a name="see-also"></a>Viz také:
- [MenuCommands vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Referenční dokumentace schématu VSCT XML](../../extensibility/vsct-xml-schema-reference.md)
