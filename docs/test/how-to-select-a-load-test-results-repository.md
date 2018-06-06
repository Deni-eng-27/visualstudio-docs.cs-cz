---
title: 'Postupy: Výběr úložiště výsledků zátěžového testu v sadě Visual Studio'
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.dialog.connectstringmissing
- vs.test.load.dialog.databaseconnectstring
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
- SQL, Load Test Results Store
ms.assetid: fa0c4dd9-612f-4a57-b8eb-458f129d9cda
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 24b146b9916fbdd656868a7a89daa0213ec7b659
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751998"
---
# <a name="how-to-select-a-load-test-results-repository"></a>Postupy: Výběr úložiště výsledků zátěžového testu

Nejste omezený na místní výsledky úložiště. Často zátěžové testy se spouštějí na sadu vzdáleného počítače agenta. Agenty mohou spolu s kontrolérem generovat více simulované zátěže než jakýkoli jeden počítač. Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Výsledky testů z agenty nebo místního počítače můžete uložit do všech ostatních SQL serverech, na který jste vytvořili uložení výsledků zátěžového testu. V obou případech je v okně Správa testovacích kontrolérů nutné určit, kam mají být uloženy výsledky zátěžového testu.

Další informace o agentů najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

## <a name="identify-a-results-store-for-load-test-data"></a>Identifikace úložiště výsledků pro data zátěžového testu

1.  V **Průzkumníku**, otevřete testovací soubor zatížení.

2.  Z **zátěžový Test** nástrojů vyberte **Správa testovacích Kontrolérů**. Zobrazí se dialogové okno Spravovat testovací kontroler. Používáte-li agent vzdáleně, je zapotřebí zvolit kontrolér.

     ![Úložiště výsledků zátěžového testu vlastnosti připojení](../test/media/loadtestconnectionproperties.png) vlastnosti připojení úložiště výsledků zátěžového testu

3.  V **úložiště výsledků zátěžového testu**, klikněte na tlačítko (...) k zobrazení **vlastnosti připojení** dialogové okno.

4.  V **název serveru**, zadejte název serveru, kde jste spustili `LoadTest` skripty.

    > [!TIP]
    > Pokud používáte systém SQL Express na místním počítači pro úložiště testu zatížení, zadejte \<computername > \sqlexpress (například **MyComputer\sqlexpress**).

5.  V části **Přihlaste se k serveru**, můžete zvolit **ověřování systému Windows**. Můžete zadat uživatelské jméno a heslo, ale pokud tak učiníte, musíte vybrat možnost **uložit heslo**.

6.  V části **připojit k databázi**, zvolte **vyberte nebo zadejte název databáze**. Vyberte **LoadTest** z rozevíracího seznamu.

7.  Zvolte **OK**. Můžete otestovat připojení tak, že zvolíte **otestovat připojení**.

8.  Zvolte **Zavřít** v **spravovat Test Controller** dialogové okno.

## <a name="see-also"></a>Viz také:

- [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)