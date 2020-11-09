---
title: Typy vlastností se neshodují.
description: Nelze vytvořit typy vlastností přidružení, které se neshodují. Zobrazit informace o této zprávě aplikace Visual Studio Návrhář relací objektů (Návrhář O/R).
ms.date: 11/04/2016
ms.topic: error-reference
ms.assetid: 97ec5a04-6e23-45a2-9226-d77ead854392
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: bce5a285f3bccdc2be8004f0eba4546bb7964a42
ms.sourcegitcommit: 0893244403aae9187c9375ecf0e5c221c32c225b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2020
ms.locfileid: "94382049"
---
# <a name="cannot-create-an-association-ltassociation-namegt---property-types-do-not-match"></a>Nelze vytvořit &lt; název přidružení přidružení &gt; – typy vlastností se neshodují.

Nelze vytvořit \<association name> typy vlastností přidružení, které se neshodují. Vlastnosti nemají shodné typy: \<property names> .

Přidružení jsou definována vybranými **vlastnostmi přidružení** v dialogovém okně **Editor přidružení** . Vlastnosti na každé straně přidružení musí být stejného datového typu.

Vlastnosti uvedené ve zprávě nemají stejné datové typy.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Zkontrolujte zprávu a poznamenejte si vlastnosti, které jsou vyvolány ve zprávě.

2. Kliknutím na tlačítko **OK** zavřete dialogové okno.

3. Zkontrolujte **Vlastnosti přidružení** a vyberte vlastnosti stejného datového typu.

4. Klikněte na **OK**.

## <a name="see-also"></a>Viz také

- [Nástroje LINQ to SQL v aplikaci Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Postupy: vytvoření přidružení mezi třídami LINQ to SQL (Návrhář O/R)](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)