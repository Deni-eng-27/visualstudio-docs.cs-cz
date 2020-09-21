---
title: vyžadovat – NuGet
description: Nástroj devinit vyžaduje – NuGet.
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
ms.openlocfilehash: c926bc146a7d85d67c49281effe88958f2031695
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2020
ms.locfileid: "90810447"
---
# <a name="require-nuget"></a>vyžadovat – NuGet

`require-nuget`Nástroj pro stažení rozhraní NUGET CLI a přidá do proměnné PATH. NuGet CLI poskytuje kompletní rozsah funkcí NuGet pro instalaci, vytváření, publikování a správu balíčků bez nutnosti provádět změny v souborech projektu. Další informace o rozhraní příkazového řádku NuGet si [můžete přečíst zde](https://docs.microsoft.com/nuget/reference/nuget-exe-cli-reference).

## <a name="usage"></a>Využití

Pokud `input` `additionalOptions` jsou vlastnosti i vynechány nebo jsou prázdné, nástroj bude postupovat podle [výchozího](#default-behavior) chování popsané níže.

| Název                                             | Typ   | Vyžadováno | Hodnota                                                                                |
|--------------------------------------------------|--------|----------|--------------------------------------------------------------------------------------|
| **vyjádření**                                     | řetězec | No       | Volitelná vlastnost komentářů Nepoužívá se.                                                |
| [**vstup**](#input)                              | řetězec | No       | Verze rozhraní příkazového řádku NuGet pro instalaci. Podrobnosti najdete níže v části o [zadání](#input) . |
| [**additionalOptions**](#additional-options)     | řetězec | No       | Podrobnosti najdete níže v části [Další možnosti](#additional-options) .                     |

### <a name="input"></a>Vstup

`input`Je volitelná vlastnost, která se používá ke konkrétní verzi rozhraní NUGET CLI, která se má nainstalovat. Pokud `input` je tento parametr vynechán, bude nainstalována nejnovější verze rozhraní příkazového řádku.

### <a name="additional-options"></a>Další možnosti

Nepoužívá se.

### <a name="default-behavior"></a>Výchozí chování

Výchozím chováním `require-nuget` nástroje je instalace nejnovějšího rozhraní příkazového řádku NuGet.

## <a name="example-usage"></a>Příklad použití

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "comments": "A sample dot-devinit file that downloads NuGet CLI and adds to PATH variable.'",
    "run": [
        {
            "tool": "require-nuget",
            "input": "5.5.1",
            "comments": "Installs NuGet for given input version. If no input given, then installs latest."
        }
    ]
}
```
