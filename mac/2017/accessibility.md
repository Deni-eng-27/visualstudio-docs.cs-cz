---
title: Usnadnění
description: V tomto článku se seznámíte s funkcemi pro usnadnění přístupu v Visual Studio pro Mac a o tom, jak je možné je povolit.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 08/15/2017
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.topic: overview
ms.openlocfilehash: a2f151cbf593d2b8e26be7ac60eaf8ff3c687499
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85938925"
---
# <a name="accessibility"></a>Usnadnění

Kromě funkcí a nástrojů v macOS má Visual Studio pro Mac následující funkce, které lidem s postižením mají lepší přístup:

- Zvětšení textu v panelu řešení a editoru
- Možnosti velikosti textu v editorech
- Přizpůsobení barev v editorech
- Přizpůsobení klávesových zkratek
- Dokončování kódu pro metody a parametry

Další informace o funkcích přístupnosti v macOS najdete na [webu společnosti Apple](https://www.apple.com/accessibility/mac/).

## <a name="using-accessibility-features-in-visual-studio-for-mac"></a>Používání funkcí usnadnění v Visual Studio pro Mac

Funkce přístupnosti v Visual Studio pro Mac jsou ve výchozím nastavení vypnuté. Pokud je chcete povolit, proveďte následující kroky:

1. Přejít na **> předvolby pro Visual Studio > jiné > přístupnost**.

2. Zaškrtněte políčko **Povolit usnadnění** , jak je znázorněno na následujícím obrázku:

    ![Zaškrtávací políčko Povolit přístupnost](media/accessibility-image1.png)

3. Pokud chcete, aby se funkce usnadnění projevily, stiskněte tlačítko **restartovat Visual Studio** .

Alternativně můžete pomocí příkazového řádku povolit funkce usnadnění přístupu. Provedete to tak, že v terminálu zadáte následující příkaz:

```bash
defaults write com.microsoft.visual-studio com.monodevelop.AccessibilityEnabled 1
```

Po zapnutí přístupnosti budete muset restartovat Visual Studio.

## <a name="how-to-use-keyboard-navigation"></a>Postupy: použití navigace pomocí klávesnice

Navigace na klávesnici se dá povolit nastavením možnosti úplný přístup pomocí klávesnice v **systémových preferencích > klávesových zkratek >** na **všechny ovládací prvky**:

![Panel předvoleb systému v MacOS](media/accessibility-image2.png)

Nastavení úplného přístupu z klávesnice se zapne v obdélníku fokusu. Pak můžete vybrat ovládací prvky pomocí:

- Karta k přechodu mezi ovládacími prvky
- Klávesa SHIFT pro přechod zpět přes ovládací prvky
- Klávesy se šipkami pro pohyb mezi ovládacími prvky ve směru šipky.

Stisknutí mezerníku aktivuje ovládací prvek s fokusem.

## <a name="how-to-enable-and-use-voice-over"></a>Postupy: povolení a použití hlasu

Zapnutí nebo vypnutí VoiceOver stisknutím klávesy **cmd + F5**

Chcete-li procházet VoiceOver pomocí příkazů uživatelského rozhraní, použijte následující příkazy:

- Přesunout kurzor VoiceOver mezi ovládacími prvky: **CTRL + ALT + šipka doleva a klávesa šipka doprava**

   VoiceOver přečte název ovládacích prvků, informace o nich a to, co s ním můžete dělat.

- Zadejte skupiny a ovládací prvky (například Oblast řešení, panel nástrojů a další panely): **CTRL + ALT + SHIFT + šipka dolů** .

   Jednou v ovládacím prvku můžete použít **CTRL + ALT + šipky** a pohybovat se uvnitř něj.

Obecné informace o používání VoiceOver v macOS najdete v následujících příručkách:

- [Začínáme s VoiceOver](https://help.apple.com/voiceover/info/guide/10.12/)
- [Příkazy VoiceOver v macOS](https://lab.dotjay.com/notes/voiceover-commands/)

## <a name="see-also"></a>Viz také

- [Funkce usnadnění v aplikaci Visual Studio (ve Windows)](/visualstudio/ide/reference/accessibility-features-of-visual-studio)