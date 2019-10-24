---
title: Čtení modelů a diagramů v jiných edicích sady Visual Studio
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 29c190115836972f86590233e331f172422efbd6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747426"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Čtení modelů a diagramů v jiných edicích sady Visual Studio

Když otevřete model ve verzi sady Visual Studio, která nepodporuje vytváření modelů, model se otevře v režimu jen pro čtení. V tomto režimu můžete změnit rozložení diagramů, ale model nemůžete změnit.

Chcete-li zjistit, které verze sady Visual Studio podporují vytváření modelů, přečtěte si téma [podpora verzí pro architektury a nástroje pro modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Získání přístupu k modelu a diagramům

Chcete-li si přečíst Diagram závislostí, je nutné nejprve pomocí sady Visual Studio otevřít projekt modelování a pak jej otevřít v rámci tohoto diagramu.

Z tohoto důvodu, pokud chcete číst diagram závislostí, musíte mít také přístup k projektu modelování, ve kterém byl vytvořen. To lze provést buď přístupem k projektu ze správy zdrojového kódu, nebo získáním kopie souborů projektu.

> [!NOTE]
> To se nevztahuje na mapy kódu a diagramy tříd .NET vygenerované z kódu. Tyto diagramy lze zobrazit nezávisle na projektu modelování.

Chcete-li si přečíst Diagram závislostí, je minimální sada souborů, kterou potřebujete, následující:

- Dva soubory diagramu pro diagram, který chcete číst, například **MyDiagram. classdiagram a MyDiagram. classdiagram. Layout**.

    > [!NOTE]
    > U diagramů závislostí byste měli mít také soubor s názvem _MyDiagram_ **. layerdiagram. potlačení**.

- Soubor projektu modelování (**MyModel. modelproj**)

- Soubor kořenového modelu (**ModelDefinition\MyModel.UML**)

- Soubory balíčku pro každý balíček, na který se odkazuje v diagramu (**ModelDefinition\MyPackage.UML**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Změny, které lze provést v režimu jen pro čtení

Pokud otevřete model a jeho diagramy ve verzi sady Visual Studio, která nepodporuje vytváření modelů, nelze model změnit. To znamená, že nemůžete změnit prvky a vztahy, které jsou zobrazeny v diagramech nebo v Průzkumníku modelů. V rozložení diagramů ale můžete udělat nějaké změny:

- Uspořádejte obrazce a spojnice v diagramu.

- Rozbalí a sbalí obrazce.

Tyto změny můžete uložit. Pokud chcete, aby se změny projevily ostatním uživatelům, musíte aspoň odeslat aktualizované soubory **. Layout** .

## <a name="see-also"></a>Viz také:

- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)