---
title: -Diff (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /Diff switch
- /Diff Devenv switch
- Diff Devenv switch
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4bb74501c15e961d8da8e1e29dd0d9979c79a305
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75570086"
---
# <a name="diff-devenvexe"></a>Diff (devenv. exe)

Porovná dva soubory. Rozdíly se zobrazí ve speciálním okně sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Diff SourceFile TargetFile [SourceDisplayName [TargetDisplayName]]
```

## <a name="arguments"></a>Arguments

- *Požadovaný sourcefile*

  Požadováno. Úplná cesta a název prvního souboru, který se má porovnat

- *TargetFile*

  Požadováno. Úplná cesta a název druhého souboru, který se má porovnat

- *SourceDisplayName*

  Volitelné. Zobrazovaný název prvního souboru.

- *TargetDisplayName*

  Volitelné. Zobrazovaný název druhého souboru

## <a name="remarks"></a>Poznámky

Je-li již instance rozhraní IDE otevřena, porovnání souborů se zobrazí na kartě v aktuálním integrovaném vývojovém prostředí (IDE).

## <a name="example"></a>Příklad

První příklad Porovná dva soubory beze změny zobrazovaných názvů. Druhý příklad porovná soubory a zároveň změní oba zobrazované názvy. Třetí a čtvrtý příklad porovnávají dva soubory, ale alias aplikujte pouze na první soubor nebo druhý soubor.

```shell
devenv /diff File1.txt File2.txt

devenv /diff File1.txt File2.txt FirstAlias "Second Alias"

devenv /diff File1.txt File2.txt "File One"

devenv /diff File1.txt File2.txt "" FileTwo
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
