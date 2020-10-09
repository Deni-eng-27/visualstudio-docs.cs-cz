---
title: require-vscomponent
description: devinit Tool vyžaduje – vscomponent.
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
ms.openlocfilehash: e88f1b58308d0c81d17f9337f0a1a1d5e253c6ba
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2020
ms.locfileid: "91862822"
---
# <a name="require-vscomponent"></a>require-vscomponent

Tento `require-vscomponent` nástroj slouží k importu konfigurací sady Visual Studio do existující sady Visual Studio. Další informace `.vsconfig` [najdete tady](../install/import-export-installation-configurations.md).

## <a name="usage"></a>Využití

Pokud `input` `additionalOptions` jsou vlastnosti i vynechány nebo jsou prázdné, nástroj bude postupovat podle [výchozího](#default-behavior) chování popsané níže.

| Název                                     | Typ   | Vyžadováno | Hodnota                                                                |
|------------------------------------------|--------|----------|----------------------------------------------------------------------|
| **vyjádření**                             | řetězec | No       | Volitelná vlastnost komentářů Nepoužívá se.                                |
| [**vstup**](#input)                      | řetězec | No       | Úplná cesta k `.vsconfig` . Podrobnosti najdete níže v části o [zadání](#input) . |
| [additionalOptions](#additional-options) | řetězec | No       | Podrobnosti najdete níže v části [Další možnosti](#additional-options) .     |

### <a name="input"></a>Vstup

Tato `input` vlastnost slouží k určení úplné cesty k `.vsconfig` souboru. Pokud není uvedeno, nástroj vyhledá `.vsconfig` v aktuálním adresáři a předáte hodnotu do instalační program pro Visual Studio.

### <a name="additional-options"></a>Další možnosti

Nepoužívá se.

### <a name="default-behavior"></a>Výchozí chování

Výchozím chováním `require-vscomponent` nástroje je vyhledat `.vsconfig` soubor v aktuálním adresáři a spustit instalační program pro Visual Studio s těmito podrobnostmi v tichém režimu. `require-vscomponent` podporuje pouze úpravu stávající instalace sady Visual Studio.

## <a name="example-usage"></a>Příklad použití

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "comments": "A sample dot-devinit file.",
    "run": [
        {
            "tool": "require-vscomponent",
            "comments": "Imports .vsconfig file which is passed as input to Visual Studio.",
            "input": "C:\\.vsconfig"
        }
    ]
}
```