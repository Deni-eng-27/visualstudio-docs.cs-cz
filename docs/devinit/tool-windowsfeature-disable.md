---
title: windowsfeature-disable
description: Nástroj devinit WindowsFeature – zakázat.
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
ms.openlocfilehash: 07a15f7c0422cbc3e44bcffd8806be35dbe5717f
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400210"
---
# <a name="windowsfeature-disable"></a>windowsfeature-disable

Tento `windowsfeature-disable` nástroj slouží k získání funkcí systému Windows.

## <a name="usage"></a>Využití

| Název                                             | Typ   | Vyžadováno | Hodnota                                                                  |
|--------------------------------------------------|--------|----------|------------------------------------------------------------------------|
| **vyjádření**                                     | řetězec | No       | Volitelná vlastnost komentářů Nepoužívá se.                                  |
| [**vstup**](#input)                              | řetězec | Yes      | Funkce Windows, která se má nainstalovat Podrobnosti najdete níže v části o [zadání](#input) . |
| [**additionalOptions**](#additional-options)     | řetězec | No       | Podrobnosti najdete níže v části [Další možnosti](#additional-options) .       |

### <a name="input"></a>Vstup

`input`Vlastnost by měla být `name` typu, který `windows feature` chcete zakázat.

### <a name="additional-options"></a>Additional-Options

Žádné

### <a name="default-behavior"></a>Výchozí chování

Výchozím chováním `windowsfeature-disable` nástroje je chyba, jak `input` je třeba.

## <a name="example-usage"></a>Příklad použití

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "comments": "Installs IIS.",
            "tool": "require-windowsfeature",
            "input": "web-server",
        }
    ]
}
```
