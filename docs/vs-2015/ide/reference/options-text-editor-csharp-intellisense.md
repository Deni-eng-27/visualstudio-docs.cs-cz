---
title: Options, Text Editor, C#, IntelliSense | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Intellisense
helpviewer_keywords:
- IntelliSense [J#], options
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dc4d918f3eae9088e2b36b7bebbb69ce130e26d9
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674141"
---
# <a name="options-text-editor-c-intellisense"></a>Možnosti, textový editor, C#, IntelliSense
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použití **IntelliSense** stránky vlastností k úpravě nastavení, která ovlivňují chování technologie IntelliSense pro jazyk Visual C#. Můžete přistupovat **IntelliSense** stránku vlastností kliknutím **možnosti** na **nástroje** nabídky, pak levým na **jazyka C#** v **Textový Editor** složku a pak levým na **technologie IntelliSense.**  
  
> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 **IntelliSense** stránka vlastností obsahuje následující vlastnosti:  
  
## <a name="completion-lists"></a>Seznamy dokončení  
 **Zobrazit seznam dokončení po zadání znaku**  
 Pokud je vybraná tato možnost, IntelliSense zobrazí seznam pro doplňování automaticky při zadávání. Pokud není vybraná tato možnost, je stále k dispozici z dokončování IntelliSense **IntelliSense** nabídky nebo stisknutím kombinace kláves CTRL + MEZERNÍK.  
  
 **Umístit klíčová slova do seznamů dokončení**  
 Pokud je vybraná tato možnost, technologie IntelliSense přidá klíčová slova jazyka C#, například [třída](https://msdn.microsoft.com/library/b95d8815-de18-4c3f-a8cc-a0a53bdf8690), do seznamu dokončení.  
  
 **Umístit fragmenty kódu do seznamů dokončení**  
 Pokud je vybraná tato možnost, technologie IntelliSense přidá do seznamu dokončení aliasy pro fragmenty kódu v C#. V případě, kdy alias fragment kódu je stejný jako klíčové slovo, například [třída](https://msdn.microsoft.com/library/b95d8815-de18-4c3f-a8cc-a0a53bdf8690), klíčové slovo je nahrazena klávesovou zkratku. Další informace najdete v tématu [fragmenty kódu Visual C#](../../ide/visual-csharp-code-snippets.md).  
  
## <a name="selection-in-completion-lists"></a>Výběr do seznamů dokončení  
 **Potvrzen zadáním následujících znaků:**  
 Určuje všechny znaky, které jsou spuštěny automatické doplňování technologie IntelliSense pro vybranou položku v seznamu dokončení po jsou typu.  
  
 **Potvrzené stisknutím mezerníku**  
 Určuje akci stisknutím klávesy MEZERNÍK ke spuštění automatického dokončování IntelliSense pro vybranou položku v seznamu pro doplňování zahrnout.  
  
 **Přidat nový řádek na konec plně napsaného slova**  
 Určuje, že pokud zadání všech znaků pro položku v seznamu dokončení a potom stiskněte klávesu ENTER nový řádek je automaticky vytvořen a kurzor se přesune na nový řádek.  
  
 Pokud zadáte například `else` a stiskněte klávesu ENTER, v editoru se zobrazí následující:  
  
 `else`  
  
 `|` (umístění kurzoru)  
  
 Nicméně pokud zadáte pouze `el` a stiskněte klávesu ENTER, v editoru se zobrazí následující:  
  
 `else|` (umístění kurzoru)  
  
## <a name="intellisense-member-selection"></a>Členská funkce technologie IntelliSense  
 **Předběžné vybere naposledy použité člena**  
 Pokud je vybraná tato možnost, technologie IntelliSense provede předvýběr členy, které jste nedávno vybrali v poli rozbalovací seznam členů pro automatický objekt název dokončení během aktuální relace v integrovaném vývojovém prostředí (IDE). Historie naposledy použité členy se vymaže mezi každou relaci v integrovaném vývojovém prostředí. Další informace najdete v tématu [technologie IntelliSense pro naposledy použité členy](../../misc/intellisense-for-most-recently-used-members.md).  
  
## <a name="see-also"></a>Viz také  
 [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)   
 [Dokumentační komentáře XML](https://msdn.microsoft.com/library/803b7f7b-7428-4725-b5db-9a6cff273199)   
 [Používání atributu IntelliSense](../../ide/using-intellisense.md)
