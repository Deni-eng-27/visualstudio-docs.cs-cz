---
title: -Out (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /Out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /Out Devenv switch
- Out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 039456c10993199ec2265042aabc0ed5c475ccd9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969290"
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)

Určuje soubor k uložení a zobrazení chyby při vám [spustit](run-devenv-exe.md), [spuštění a ukončení](runexit-devenv-exe.md), [upgradovat](upgrade-devenv-exe.md), [sestavení](build-devenv-exe.md), [znovu sestavit](rebuild-devenv-exe.md), [čisté](clean-devenv-exe.md), nebo [nasazení](deploy-devenv-exe.md) řešení.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Out FileName
```

## <a name="arguments"></a>Arguments

- *FileName*

  Povinný parametr. Cesta a název souboru, který se zobrazí výstup při vytváření spustitelného souboru.

## <a name="remarks"></a>Poznámky

Pokud je zadána neexistující soubor, soubor je vytvořen automaticky. V opačném případě soubor již existuje, a výsledky jsou připojeny k existující obsah souboru.

Chyby sestavení příkazového řádku se zobrazují v **příkaz** okno a Tvůrce řešení zobrazení **výstup** okna. Tento přepínač je užitečné při prohlížení výsledků bezobslužném sestavování.

## <a name="example"></a>Příklad

Tento příklad se spouští `MySolution` a zapíše chyby do souboru `MyErrorLog.txt`.

```shell
devenv /run "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Nebo spuštění (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/ RunExit (devenv.exe)](runexit-devenv-exe.md)
- [/ Upgrade (devenv.exe)](upgrade-devenv-exe.md)
- [/ Clean (devenv.exe)](clean-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)