---
title: Rozšíření diagramů závislostí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 150621514f9153b1e9d67f8e9c85a00275c27b15
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58416107"
---
# <a name="extend-dependency-diagrams"></a>Rozšíření diagramů závislostí

Můžete napsat kód k vytvoření a aktualizaci diagramů závislostí a k ověření struktury kód programu proti diagramů závislostí v sadě Visual Studio. Můžete přidat příkazy, které se zobrazují v nabídce místní (objektu context) diagramů, přizpůsobení gesta přetažení myší a přístup k modelu vrstvy z textových šablon. Můžete zabalit tato rozšíření do Visual Studio integrace rozšíření (VSIX) a distribuovat ostatním uživatelům aplikace Visual Studio.

 Další informace o diagramů závislostí naleznete v tématu:

-   [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)

-   [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)

-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)

-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)

##  <a name="prereqs"></a> Požadavky

Musí být nainstalovaný na počítači, kde chcete vyvíjet rozšíření vrstvy:

-   Visual Studio

-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

-   Sada Modeling SDK pro Visual Studio

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

Musí mít vhodnou verzi sady Visual Studio nainstalované na počítači, ve kterém chcete spustit rozšíření vrstvy.

Které verze sady Visual Studio podporují diagramů závislostí najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="in-this-section"></a>V tomto oddílu
 [Přidávání příkazů a gest do diagramů závislostí](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [Přidání vlastního ověřování architektury do diagramů závislostí](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [Přidání vlastních vlastností do diagramů závislostí](../modeling/add-custom-properties-to-layer-diagrams.md)

## <a name="see-also"></a>Viz také

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
- [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)
- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)
