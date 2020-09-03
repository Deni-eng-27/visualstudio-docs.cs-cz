---
title: 'Chyba: závislost &#39;&#39; souboru v projektu&#39; &#39;projektu nelze zkopírovat do běhového adresáře, protože by byla v konfliktu se závislostí &#39;Souborová&#39; | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
f1_keywords:
- vs.tasklisterror.copy_version_conflict
ms.assetid: cd7de1eb-7d58-4e2c-9811-a7201f7817be
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d4fd45741585aaf82c82257999b40d6257e82d9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72656038"
---
# <a name="error-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-conflict-with-dependency-39file39"></a>Chyba: závislost &#39;&#39; souboru v projektu&#39; &#39;projektu nelze zkopírovat do běhového adresáře, protože by byla v konfliktu se souborem závislosti &#39;&#39;
Došlo ke konfliktu mezi odkazy. pro spuštění aplikace se do adresáře bin kopíruje více než jedna odlišná závislost se stejným názvem souboru. Spuštění adresáře nemůže vyřešit konflikt, protože žádná z závislostí není primárními odkazy.

 Tato chyba způsobí selhání sestavení.

 Dvojím kliknutím na tuto položku Seznam úkolů přejdete do uzlu odkazy v projektu, ve kterém ke konfliktu dochází.

 **Oprava této chyby**

- Vytvořte jedno ze sestavení s přímým odkazem na váš projekt. Možným Nevýhodou tohoto přístupu je, že sestavení, které zvolíte, není zaručeno pracovat se sestaveními, která vyžadují jinou verzi odkazovaného sestavení.

     \- ani

- Ujistěte se, že obě kopie sestavení jsou silně pojmenované a v globální mezipaměti sestavení (GAC). Tím se eliminuje nutnost kopírovat sestavení do adresáře bin.

## <a name="see-also"></a>Viz také
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) [globální sestavení mezipaměti](https://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) sestavení se [silným názvem](https://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b) sestavení Správa [verzí](https://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903) [Postupy: vytvoření a odebrání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md)