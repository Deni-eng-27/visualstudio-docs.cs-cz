---
title: nuget-restore
description: devinit Tool NuGet – obnovení
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
ms.openlocfilehash: be31cb2c4c1e71b2e49928488b1cb061d41033a9
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93399631"
---
# <a name="nuget-restore"></a>nuget-restore

`nuget-restore`Nástroj obnoví závislosti a nástroje specifické pro projekt, které jsou zadány v souboru projektu. Přečtěte si další informace [o obnovení NuGet](/nuget/reference/cli-reference/cli-ref-restore).

## <a name="usage"></a>Využití

Pokud `input` `additionalOptions` jsou vlastnosti i vynechány nebo jsou prázdné, nástroj bude postupovat podle [výchozího](#default-behavior) chování popsané níže.

| Název                                             | Typ   | Vyžadováno | Hodnota                                                                                |
|--------------------------------------------------|--------|----------|--------------------------------------------------------------------------------------|
| **vyjádření**                                     | řetězec | No       | Volitelná vlastnost komentářů Nepoužívá se.                                                |
| [**vstup**](#input)                              | řetězec | No       | Cesta k souboru projektu nebo řešení, který má být obnoven. Podrobnosti najdete níže v části o [zadání](#input) . |
| [**additionalOptions**](#additional-options)     | řetězec | No       | Podrobnosti najdete níže v části [Další možnosti](#additional-options) .                     |

### <a name="input"></a>Vstup

Cesta k souboru projektu nebo řešení, který má být obnoven.

### <a name="additional-options"></a>Další možnosti

Další možnosti jsou předány jako – do příkazu NuGet Restore.

### <a name="default-behavior"></a>Výchozí chování

Výchozím chováním `nuget-restore` nástroje je spustit obnovení NuGet v aktuálním adresáři.

## <a name="example-usage"></a>Příklad použití

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "comments": "A sample dot-devinit file that restores NuGet pacakges.",
    "run": [
        {
            "tool": "nuget-restore",
            "comments": "Restores the dependencies and tools of a project using nuget restore.",
            "input": "C:\\nuget\\Nuget.config"
        }
    ]
}
```