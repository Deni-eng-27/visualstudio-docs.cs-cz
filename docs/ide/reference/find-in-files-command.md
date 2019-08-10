---
title: Najít v souborech – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2877057f32ba6553a2cdcefbbc1bb7a8bf2884da
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919257"
---
# <a name="find-in-files-command"></a>Najít v souborech – příkaz
Vyhledejte soubory pomocí podmnožiny možností dostupných na kartě **najít v souborech** okna **Najít a nahradit** .

## <a name="syntax"></a>Syntaxe

```cmd
Edit.FindinFiles findwhat [/case] [/ext:extensions]
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]
[/text2] [/wild|/regex] [/word]
```

## <a name="arguments"></a>Arguments

`findwhat`\
Povinný parametr. Text, který se má shodovat.

## <a name="switches"></a>Přepínače
/Case nebo/c\
Volitelné. Shody se objeví pouze v případě, že velká a malá písmena přesně odpovídají znakům zadaným v `findwhat` argumentu.

rozšířeného`extensions`\
Volitelné. Určuje přípony souborů pro soubory, které mají být prohledány. Pokud není zadaný, použije se předchozí rozšíření, pokud se dřív zadal.

oblasthledání`searchpath`\
Volitelné. Adresář, který chcete vyhledat. Pokud cesta obsahuje mezery, uzavřete celou cestu do uvozovek.

/Names nebo/n\
Volitelné. Zobrazí seznam názvů souborů, které obsahují shody.

/Options nebo/T\
Volitelné. Zobrazí seznam aktuálních nastavení možností hledání a neprovádí hledání.

/Regex nebo/r\
Volitelné. Používá předem definované speciální znaky v `findwhat` argumentu jako notace, které reprezentují vzory textu, nikoli literální znaky. Úplný seznam znaků regulárních výrazů naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

/Reset po vyčištění nebo/e\
Volitelné. Vrátí možnosti hledání do jejich výchozího nastavení a neprovádí hledání.

/stop
Volitelné. Zastaví aktuální operaci hledání, pokud právě probíhá. Při hledání se ignorují všechny `/stop` ostatní argumenty, pokud je zadaný. Pokud například chcete zastavit aktuální hledání, zadejte následující:

```cmd
>Edit.FindinFiles /stop
```

/Sub nebo/s\
Volitelné. Vyhledá podsložky v adresáři zadaném v argumentu/Lookin:`searchpath` .

/Text2 nebo/2 \
Volitelné. Zobrazí výsledky hledání v okně výsledky hledání 2.

/Wild nebo/l\
Volitelné. Používá předdefinované speciální znaky v `findwhat` argumentu jako notace, které reprezentují znak nebo sekvenci znaků.

/Word nebo/W\
Volitelné. Vyhledává pouze celá slova.

## <a name="example"></a>Příklad
Tento příklad vyhledá btnCancel ve všech souborech. CLS umístěných ve složce Moje projekty sady Visual Studio a v okně výsledky hledání 2 zobrazí informace o shodě.

```cmd
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2
```

## <a name="see-also"></a>Viz také

- [Najít v souborech](../../ide/find-in-files.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)