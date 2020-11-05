---
title: choco-install
description: devinit Tool Choco – instalace pro instalaci balíčků čokolády
ms.date: 08/28/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: 3bdcf6caa52f19bc03559fb57d41fadb0ac56485
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93399856"
---
# <a name="choco-install"></a>choco-install

`choco-install`Nástroj lze použít k instalaci a aktualizaci [čokoládových](https://chocolatey.org/) balíčků.

## <a name="usage"></a>Využití

Pokud `input` `additionalOptions` jsou vlastnosti i vynechány nebo jsou prázdné, nástroj neprovede žádnou akci.

| Název                                             | Typ   | Vyžadováno | Hodnota                                                                                                          |
|--------------------------------------------------|--------|----------|----------------------------------------------------------------------------------------------------------------|
| **vyjádření**                                     | řetězec | No       | Volitelná vlastnost komentářů Nepoužívá se.                                                                          |
| [**vstup**](#input)                              | řetězec | No       | Balíček, který se má nainstalovat Podrobnosti najdete níže v části o [zadání](#input) .                                                 |
| [**additionalOptions**](#additional-options)     | řetězec | No       | Další možnosti, které se mají předat nástroji Podrobnosti najdete níže v části [Další možnosti](#additional-options) .       |

### <a name="input"></a>Vstup

Tato `input` vlastnost slouží k zadání názvu balíčku, který má být nainstalován (například ' MongoDB ') nebo cesty ke konfiguračnímu souboru následujících formátů _packages.config_ , _. nuspec_ a _. nupkg_. Hodnota `input` bude připojena k `choco install` příkazu (například `choco install mongodb` ) spolu s případnými argumenty, které jsou specifické v nástroji [`additionalOptions`](#additional-options) a integrovanými `choco` možnostmi (definované [níže](#built-in-options)). Balíčky najdete v [galerii balíčků pro čokolády](https://chocolatey.org/packages). Při použití konfiguračního souboru můžete v této vlastnosti předat cestu k tomuto souboru `input` , například `"input":"packages.config"` .

### <a name="additional-options"></a>Další možnosti

Další možnosti konfigurace mohou být předány jako hodnota `additionalOptions` . Tyto argumenty jsou přímo Passthrough na argumenty používané [`choco install`](https://chocolatey.org/docs/commands-install) a jsou definovány v dokumentaci k čokoládě.

### <a name="built-in-options"></a>Předdefinované možnosti

`choco-install`Nástroj nastaví řadu `choco` argumentů příkazového řádku, aby bylo zajištěno, že `choco` může běžet bez periferních zařízení. Níže jsou uvedené argumenty a dokumentace k nim najdete v [dokumentaci k čokoládě](https://chocolatey.org/docs/).

| Název                  | Popis                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------|
| **--Ano**             | Potvrdit všechny výzvy – vybere kladnou odpověď místo výzvy. To `--accept-license.` |
| **--No-Progress**     | Nezobrazovat průběh – procento průběhu nebude zobrazeno.                                         |
| **--Skip-PowerShell** | Přeskočit PowerShell – chocolateyInstall.ps1 nebude spuštěná.                                              |

## <a name="example-usage"></a>Příklad použití

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "comments": "Example that will trigger the Default behavior of installing packages listed in a packages.config file.",
            "tool": "choco-install",
            "input": "packages.config",
        },
        {
            "comments": "Example that will install the package 'mongodb'.",
            "tool": "choco-install",
            "input": "mongodb"
        },
        {
            "comments": "Example that will install the '4.2.7' version of 'mongodb'.",
            "tool": "choco-install",
            "input": "mongodb",
            "additionalOptions": "--version 4.2.7"
        }
    ]
}
```
