---
title: Možnosti, textový Editor, ve formátu HTML (webové formuláře), ověření
ms.date: 1/15/2019
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.HTML.Validation
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fad568f43e1064fe264c528d68a39b072bf905db
ms.sourcegitcommit: d0b02affd24e66efed924c197824f35f823e3240
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/21/2019
ms.locfileid: "54417821"
---
# <a name="options-text-editor-html-web-forms-validation"></a>Možnosti, textový Editor, ve formátu HTML (webové formuláře), ověření

Použití **ověření** možnosti stránky můžete nastavit předvolby jak editoru HTML kontroly syntaxe kódu HTML dokumentu. Pro přístup k této stránce, na panelu nabídek zvolte **nástroje** > **možnosti**a potom rozbalte **textový Editor** > **HTML (webové formuláře)**   >  **Ověření**.

## <a name="validation"></a>Ověřování

- **Pro zjištění schématu ověření použít typ dokumentu**

   Schéma určuje, které elementů, atributů a malá a velká písmena jsou platné v tomto schématu. Také určuje tagy a atributy, které jsou k dispozici v technologii IntelliSense.
  
   Tuto možnost vyberte, pokud chcete Visual Studio k používání obsahu na stránce **<! DOCTYPE >** prohlášení a **html** element určit schéma. Například pokud vyberete tuto možnost a na stránce má deklaraci `<!DOCTYPE html>`, Visual Studio používá schéma HTML5. Ale pokud **html** značka nemá **xmlns** atribut, například `<html xmlns="http://www.w3.org/1999/xhtml">`, Visual Studio používá schéma XHTML5.

- **Cíl, když typ dokumentu**

   Vyberte schéma ověření proti při žádné **<! DOCTYPE >** deklarace na stránce.

  - **Zobrazit chyby**

     Zaškrtněte políčko Povolit ověřování. Pokud políčko není zaškrtnuto, nebude editoru označte chyby ověření.
    
     Zaškrtávací políčka umožní doladit tak, že zadáte jednotlivé typy chyb, které chcete, aby editor k označení ověřování.

     > [!NOTE]
     > Některé schémata nenabízejí možnosti označit jednotlivých typů chyb. Například, pokud se rozhodnete **XHTML 1.1** jako cílové schéma, jsou všechna zaškrtávací políčka možnost zakázána. V takovém případě jsou označeny všechny typy chyb.

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)