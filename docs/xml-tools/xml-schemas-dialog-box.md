---
title: XML schémata
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.xmleditor.schemasdialog
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11743756ffd8f59520448d2687dbada6d4eaca40
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72608039"
---
# <a name="xml-schemas-dialog-box"></a>Dialogové okno Schémata XML

Dialogové okno **schémata XML** slouží k výběru schémat XML Schema Definition Language (XSD), která mají být přidružena k dokumentu XML. Můžete vybrat schéma z mezipaměti schématu nebo zadat schéma, které se nenachází v mezipaměti. Vybraná schémata se považují za součást sady schémat. Sada schémat se používá pro technologii IntelliSense a také pro ověřování dokumentů XML.

Můžete otevřít dialogové okno **schémata XML** kliknutím na tlačítko **schémata** v okně Vlastnosti dokumentu, nebo výběrem **schémat** z nabídky **XML** .

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Použije**

Vyberte způsob použití schématu XML.

- **Automaticky**. Toto schéma není používáno aktuálním dokumentem, ale je k dispozici pro automatické přidružení. Pokud dokument XML deklaruje obor názvů, který odpovídá `targetNamespace` tohoto schématu, schéma bude automaticky přidruženo a je zahrnuto do sady schémat.

- **Použijte toto schéma**. Toto schéma je používáno aktuálním dokumentem. Uživatel explicitně požadoval, aby se toto schéma používalo kliknutím na tento sloupec, nebo jestli se schéma automaticky přidružil na základě odpovídajícího `targetNamespace`.

- **Nepoužívejte Vybraná schémata**. Toto schéma není používáno aktuálním dokumentem, a to ani v případě, že má schéma shodnou `targetNamespace`. Toto nastavení může být užitečné při řešení konfliktů, pokud existuje více než jedna verze stejného schématu v mezipaměti schématu nebo řešení.

**Cílový obor názvů**

Zobrazí cílový obor názvů přidružený ke schématu XML.

**Název souboru**

Zobrazí název souboru schématu XML.

**Add**

Otevře dialogové okno **otevřít schéma XSD** , které umožňuje vybrat další schémata, která se mají přidat do sady schémat. Když do sady schémat přidáte schéma, hodnota **použít** sloupec je nastavená na **použít toto schéma**.

**Odebrány**

Odebere aktuálně vybrané schéma ze sady schémat. Tím se odebere schéma z mezipaměti schématu v paměti, ale ne ze systému souborů.

## <a name="see-also"></a>Viz také:

- [Postupy: Výběr schémat XML k použití](../xml-tools/how-to-select-the-xml-schemas-to-use.md)
- [Mezipaměť schématu](../xml-tools/schema-cache.md)