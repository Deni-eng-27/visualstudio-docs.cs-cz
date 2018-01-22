---
title: "Práce s Python v sadě Visual Studio, krok 6, práce s Gitem | Microsoft Docs"
description: "Krok 6 základní kurz pro práci s Pythonem v sadě Visual Studio, který po sobě zakrývá funkce související s Git sady Visual Studio."
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: ef6b3bddfb90c64872de331c988f10595e179eb8
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="step-6-working-with-git"></a>Krok 6: Práce s Gitem

**Předchozí krok: [instalaci balíčků a správu prostředí Python](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio poskytuje přímá integrace s místní úložiště Git a ty, které jsou umístěny na služby, jako je Githubu a Visual Studio Team Services. Integrace zahrnuje klonování úložiště, potvrzení změn a správa větve.

Toto téma popisuje vytvoření místní úložiště Git pro existující projekt. Návod pro vytvoření projektu ze vzdáleného úložiště Git najdete v tématu [rychlý start: klonovat úložiště Python kódu v sadě Visual Studio](quickstart-03-project-from-repository.md).

1. S otevřete v sadě Visual Studio, jako je například projekt z projektu [předchozího kroku](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), klikněte pravým tlačítkem na řešení a vyberte **přidat řešení správy zdrojového kódu**. Visual Studio vytvoří místní úložiště Git, která obsahuje váš kód projektu a ovládací prvky související s Git zobrazí také zobrazí podél dolního okraje okna Visual Studio. Ovládací prvky zobrazení čekající na potvrzení, změny, název úložiště a větev. Podržte ukazatel nad ovládací prvky zobrazíte další informace.

  ![Další informace se zobrazí, když ukazatele myši na ovládací prvek Git v okně Visual Studio](media/working-with-git-01.png)

1. **Team Explorer** také zobrazí se okno s Git zobrazíte možnosti výběrem hlavičku úložiště. **Synchronizace** podokně, jak je znázorněno, poskytuje možnosti pro publikování do vzdáleného úložiště.

  ![Průzkumník týmových projektů v sadě Visual Studio po vytvoření místní úložiště](media/working-with-git-02.png)

1. Vyberte **změny** nepotvrzené změny a potvrdit Pokud žádoucí.

  ![Průzkumník týmových projektů v sadě Visual Studio zobrazující nepotvrzené změny](media/working-with-git-03.png)

1. Vyberte **větví** sloužící ke zkoumání větve a provádět operace sloučení a rebase:

  ![Průzkumník týmových projektů v sadě Visual Studio zobrazující větví](media/working-with-git-04.png)

1. Pokud používáte místní úložiště, potvrzené změny přejděte přímo do úložiště. Pokud jste připojení k Vzdálené úložiště, vyberte **synchronizace** tak, aby nabízel vaše místní potvrzení.

## <a name="going-deeper"></a>Budete hlubší

Rozsáhlejší kurz týkající se práce s Gitem, najdete v části [sdílet kódu s Visual Studio 2017 a služby VSTS Git](/vsts/git/share-your-code-in-git-vs-2017)

## <a name="tutorial-review"></a>Kurz revize

Blahopřejeme k dokončení tohoto kurzu na Python v sadě Visual Studio. V tomto kurzu naučili jste se postup:

- Vytváření projektů a zobrazit obsah projektu.
- Pomocí editoru kódu a spuštění projektu.
- Použití interaktivních okna nový kód vyvíjet a snadno zkopírovat tento kód do editoru.
- Spusťte program, dokončené v ladicím programu sady Visual Studio.
- Instalovat balíčky a spravovat prostředí Python
- Práce s kódem v úložišti Git

Tady prozkoumejte koncepty a návody, včetně následujících:

- [Vytvoření rozšíření C++ pro Python](working-with-c-cpp-python-in-visual-studio.md)
- [Publikování do služby Azure App Service](publishing-to-azure.md)
- [Profilace](profiling.md)
- [Testování jednotek](unit-testing.md)
