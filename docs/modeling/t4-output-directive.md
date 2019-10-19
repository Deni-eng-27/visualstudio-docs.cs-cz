---
title: T4 – direktiva Output
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1da8ec010e878ff80a9f46748993705b87193d99
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606216"
---
# <a name="t4-output-directive"></a>T4 – direktiva Output

V textových šablonách sady Visual Studio je použita direktiva `output` k definování přípony názvu souboru a kódování transformačního souboru.

 Například pokud váš projekt sady Visual Studio obsahuje soubor šablony s názvem **MyTemplate.TT** , který obsahuje následující direktivu:

 `<#@output extension=".cs"#>`

 pak Visual Studio vygeneruje soubor s názvem **MyTemplate.cs**

 Direktiva `output` není v textové šabloně běhu (předzpracovaná) vyžadována. Místo toho aplikace získá generovaný řetězec voláním `TextTransform()`. Další informace najdete v tématu [generování textu v době běhu s textovými šablonami T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="using-the-output-directive"></a>Použití direktivy Output

```
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>
```

 V každé textové šabloně by neměla existovat více než jedna direktiva `output`.

## <a name="extension-attribute"></a>atribut Extension
 Určuje příponu názvu souboru generovaného textového výstupního souboru.

 Výchozí hodnota je **. cs**

 Příklady: `<#@ output extension=".txt" #>`

 `<#@ output extension=".htm" #>`

 `<#@ output extension=".cs" #>`

 `<#@ output extension=".vb" #>`

 Přijatelné hodnoty: jakákoli platná přípona názvu souboru.

## <a name="encoding-attribute"></a>atribut Encoding
 Určuje kódování, které má být použito při vygenerování výstupního souboru. Příklad:

 `<#@ output encoding="utf-8"#>`

 Výchozí hodnota je kódování používané souborem textové šablony.

 Přijatelné hodnoty: `us-ascii`

 `utf-16BE`

 `utf-16`

 `utf-8`

 `utf-7`

 `utf-32`

 `0` (výchozí systémové nastavení)

 Obecně můžete použít řetězec WebName nebo číslo znakové stránky kteréhokoli z kódování vrácených funkcí <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>.