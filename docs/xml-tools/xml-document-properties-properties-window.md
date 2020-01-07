---
title: Vlastnosti dokumentu XML, okno Vlastnosti
ms.date: 03/05/2019
ms.topic: reference
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1b21f4435737597136e1ac4a4dd8651decaf4c65
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592422"
---
# <a name="xml-document-properties-properties-window"></a>Vlastnosti dokumentu XML, okno Vlastnosti

Okno **vlastnosti** poskytuje základní informace o dokumentu, který je aktivní v editoru XML. Vlastnosti, které jsou k dispozici, se liší v závislosti na typu dokumentu XML, který je aktuálně aktivní.

> [!NOTE]
> Všechny vlastnosti dokumentu XML jsou uloženy v řešení. V důsledku toho není nutné znovu zadávat tyto hodnoty při příštím otevření řešení.

**Kódování**

Kódování znaků souboru. Změna této vlastnosti také změní atribut Encoding v deklaraci XML a naopak. Nové kódování se použije ke kódování souboru při uložení souboru.

**Vstup**

Vstupní dokument přidružený k šabloně stylů XSLT. Je používán příkazy **Spustit XSLT** , například **XML** > **Spustit XSLT bez ladění**. Dokument lze vybrat pomocí tlačítka Procházet ( **...** ).

Tato vlastnost je viditelná pouze v případě, že je soubor XSLT otevřen v editoru.

**Output**

Soubor, který je generován při transformaci dokumentu XML.

Pokud není zadán soubor, je vygenerován výchozí název souboru na základě atributu `method` u elementu `xsl:output`, který určuje příponu souboru. Výchozí soubor se nachází v dočasném adresáři aktuálního uživatele.

**Schémata**

Schémata, která se mají použít pro ověření Tlačítko otevře dialogové okno **schémata XSD** , které lze použít k výběru schémat, která chcete použít.

Můžete také zadat cestu k schématům. Pokud je zadáno více schémat, je nutné každou cestu schématu uzavřít do dvojitých uvozovek.

**Šablony**

Soubor XSLT, který se používá k transformaci dokumentu při **spuštění ladění XSLT** a **spuštění XSLT bez** příkazů pro ladění. Pokud je toto pole prázdné, použije editor hodnotu poskytnutou v dokumentu pokyn pro zpracování `xml-stylesheet` nebo se zobrazí výzva k zadání názvu souboru.

Při úpravách souboru XSLT lze pomocí této vlastnosti určit, že by měla být použita jiná šablona stylů, pokud je vybrána možnost **Spustit ladění XSLT** nebo **Spustit XSLT bez příkazu ladit** . Můžete to třeba udělat, když upravujete šablonu stylů, která je obsažena v nadřazené šabloně stylů.

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)
