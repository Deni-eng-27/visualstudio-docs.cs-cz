---
title: devinit a GitHub Codespaces
description: Naučte se, jak přizpůsobit codespace pro Visual Studio pomocí devinit.
ms.date: 08/28/2020
ms.topic: reference
author: andster
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: b42ce84bcb2a336e37d0ffafb2bab6c2dba9ba9d
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852207"
---
# <a name="devinit-and-github-codespaces"></a>devinit a GitHub Codespaces

devinit je skvělý bezplatný [Codespaces](https://github.com/features/codespaces) a devinit se dá použít k získání codespace nastavení, takže přispěvatelé můžou hned sestavovat, spouštět a ladit.

Pro integraci s Codespaces GitHubu je `devinit` potřeba volat z `postCreateCommand` definovaného v `.devcontainer.json` souboru umístěném v kořenovém adresáři úložiště. Řetězce v `postCreateCommand` jsou spouštěny ve výchozím prostředí po naklonování úložiště v codespace. Další informace najdete `postCreateCommand` v [dokumentaci pro přizpůsobení](https://docs.github.com/github/developing-online-with-codespaces/configuring-codespaces-for-your-project)Codespaces GitHubu. Chcete-li přidat `devinit` příkaz, můžete přidat `devinit init` do, `postCreateCommand` jak je znázorněno v níže uvedených příkladech.

Můžete se také spouštět `devinit init -f <path to .devinit.json>` z integrovaného terminálu sady Visual Studio, jakmile se připojíte k vašemu codespace.

## <a name="examples"></a>Příklady

### <a name="with-a-devinitjson-file"></a>S .devinit.jsem v souboru
V tomto příkladu se _.devcontainer.js_ v souboru nachází v kořenovém adresáři úložiště vedle _.devinit.jsv_ souboru. Soubory mohou být také umístěny v adresáři _. devcontainer_ .

```json
{
  "postCreateCommand": "devinit init"
}
```

```json
{
  "postCreateCommand": ["<some other command>", "devinit init"]
}
```

### <a name="as-commands"></a>Jako příkazy
V tomto příkladu _.devcontainer.jsv_ souboru níže je umístěn v kořenovém adresáři úložiště a `devinit run` je volán programově pro spuštění nástroje.  

```json
{
  "postCreateCommand": ["devinit run –t require-dotnetcoresdk"]
}
```

### <a name="from-a-terminal-prompt"></a>Z výzvy terminálu

Když aktuální pracovní adresář obsahuje _.devinit.jsv_ souboru.

```batch
> devinit init
```

Když je _.devinit.js_ v jiném adresáři.

```batch
> devinit init -f path/to/.devinit.json
```
