---
title: Úpravy šablon stylů XSLT
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a8625defb0d9e8d656aac7bb3d2236d4f5bb9c9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021881"
---
# <a name="edit-xslt-style-sheets"></a>Úpravy šablon stylů XSLT

XML Editor lze také upravit šablony stylů XSLT. Můžete využít výhod výchozí funkce editoru, jako je IntelliSense, osnovy, fragmenty kódu XML a tak dále. Kromě toho existují také nové funkce, které usnadňují vývoj v jazyce XSLT.

## <a name="xslt-features"></a>Funkce XSLT
 Následující tabulka popisuje funkce specifické pro práci s šablon stylů XSLT.

 **Barevné zvýrazňování syntaxe**

 XSLT klíčová slova, například `template`, `match`, a tak dále se zobrazují v barvu – klíčové slovo XSLT určené **písma a barvy** nastavení.

 **Podtržení vlnovkami**

 XML Editor používá nainstalovaného *xslt.xsd* souboru ověření šablony stylů XSLT. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. XML Editor také zkompiluje stylů v pozadí a chyby kompilátoru sestav nebo upozornění s odpovídající podtržení vlnovkou.

 **Podpora pro bloky skriptu**

 Kód v blocích skriptu je podporováno v ladicím programu XSLT, můžete nastavit zarážky a krokovat kód bloku skriptu.

 **Zobrazit výstup XSLT**

 Můžete provést transformaci XSL a zobrazit výstup z editoru XML. Další informace najdete v tématu [jak: Provedení transformace XSLT z editoru XML](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md).

 **Ladění XSLT**

 Můžete spustit ladicí program XSLT ze souboru XSLT v editoru XML. Ladicí program podporuje nastavení zarážky v souboru XSLT, zobrazení stavu provedení transformace XSLT a tak dále. Proměnná XSLT ukazatel myši zobrazí popisek s hodnotou proměnné. Ladicí program lze použít k ladění šablony stylů nebo chcete-li ladit kompilované transformace XSL vyvolána z jiné aplikace. Další informace najdete v tématu [ladění XSLT](../xml-tools/debugging-xslt.md).

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)