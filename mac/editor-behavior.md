---
title: Formátování kódu
description: V tomto článku jsou popsány různé možnosti, které lze použít k úpravě chování textového editoru v Visual Studio pro Mac
author: cobey
ms.author: cobey
ms.date: 05/06/2018
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 20363d5497ea5897cb2685ca838da44b8c21d3df
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "67823176"
---
# <a name="editor-behavior"></a>Chování editoru

Chování editoru lze nastavit tak, aby bylo možné formátovat kód při zápisu. Tyto akce jsou nastaveny v části **Visual Studio > předvolby > textový Editor > chování**a některé z nejčastěji používaných funkcí jsou popsány níže:

![Možnosti chování editoru](media/source-editor-image9.png)

* Při vytváření nových tříd, metod nebo vlastností lze do kódu automaticky přidat párové uzavírací závorky. Když je vybraná tato možnost, `{` bude se automaticky přidávat `}` .
* Formátování kódu průběžně se spouští pomocí znaků, například středníkem nebo složených závorek, které budou emulovat nastavené předvolby formátování.
* Můžete také zvolit formátování souboru při jeho ukládání, což umožňuje psaní kódu podle potřeby a nechá integrované vývojové prostředí (IDE) zodpovědné za formátování kódu, jak je nastaveno pomocí stávajících předvoleb.
* Odsazení lze nastavit na hodnotu None, auto nebo Smart. Následující akce:
  * None – nastaví blikající kurzor na začátek dalšího řádku.
  * Automaticky nastaví blikající kurzor na stejný sloupec na dalším řádku.
  * Inteligentní odsazení na následujícím řádku na základě kódu
* Chování při zalamování slov se liší mezi operačních systémech a pro účely navigace, musí textový editor znát, kde začíná nebo končí slova. Formátování lze nastavit na systém UNIX nebo Windows.

Můžete také nastavit pravidla formátování pro XML, CSS, HTML a JSON.

## <a name="see-also"></a>Viz také

- [Předvolby stylu kódu (Visual Studio ve Windows)](/visualstudio/ide/code-styles-and-quick-actions)
