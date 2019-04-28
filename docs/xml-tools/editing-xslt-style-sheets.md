---
title: Úpravy šablon stylů XSLT
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dab4013bf3921a2af4f69d464c10d1e70f9407b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996991"
---
# <a name="edit-xslt-style-sheets"></a>Úpravy šablon stylů XSLT

XML editor lze také upravit šablony stylů XSLT. Můžete využít výhod výchozí funkce editoru, jako je IntelliSense, osnovy, fragmenty kódu XML a tak dále. Kromě toho existují také nové funkce, které usnadňují vývoj v jazyce XSLT.

## <a name="xslt-features"></a>Funkce XSLT

Následující tabulka popisuje funkce specifické pro práci s šablon stylů XSLT.

**Barevné zvýrazňování syntaxe**

Klíčová slova XSLT, například `template` a `match`, jsou zobrazeny v barvu – klíčové slovo XSLT určené **písma a barvy** nastavení.

**Podtržení vlnovkami**

XML editor používá nainstalovaného *xslt.xsd* souboru ověření šablony stylů XSLT. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. XML editor také zkompiluje stylů v pozadí a chyby kompilátoru sestav nebo upozornění s odpovídající podtržení vlnovkou.

**Podpora pro bloky skriptu**

Kód v blocích skriptu je podporováno v ladicím programu XSLT, můžete nastavit zarážky a krokovat kód bloku skriptu.

**Zobrazit výstup XSLT**

Můžete provést transformaci XSL a zobrazit výstup z editoru XML. Další informace najdete v tématu [jak: Provedení transformace XSLT z editoru XML](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md).

**Ladění XSLT**

Můžete spustit ladicí program XSLT ze souboru XSLT v editoru XML. Ladicí program podporuje nastavení zarážky v souboru XSLT, zobrazení stavu provedení transformace XSLT a tak dále. Proměnná XSLT ukazatel myši zobrazí popisek s hodnotou proměnné. Ladicí program lze použít k ladění šablony stylů nebo chcete-li ladit kompilované transformace XSL vyvolána z jiné aplikace. Další informace najdete v tématu [ladění XSLT](../xml-tools/debugging-xslt.md).

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)