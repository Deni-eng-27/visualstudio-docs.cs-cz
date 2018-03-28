---
title: Práce s Python, krok 6, práce s Gitem | Microsoft Docs
description: Krok 6 základní kurz pro práci s Pythonem v sadě Visual Studio, který po sobě zakrývá funkce související s Git sady Visual Studio.
ms.custom: mvc
ms.date: 01/16/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: ec8534e7fd3121510a05e201e8bdea2e9a7fce1c
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="step-6-working-with-git"></a>Krok 6: Práce s Gitem

**Předchozí krok: [instalaci balíčků a správu prostředí Python](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio poskytuje přímá integrace s místní úložiště Git a vzdálené úložiště na služby, jako je Githubu a Visual Studio Team Services. Integrace zahrnuje klonování úložiště, potvrzení změn a správa větve.

Tento článek obsahuje základní přehled vytváření místní úložiště Git pro existující projekt a seznámení se s některé funkce související s Git sady Visual Studio.

1. S otevřete v sadě Visual Studio, jako je například projekt z projektu [předchozího kroku](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), klikněte pravým tlačítkem na řešení a vyberte **přidat řešení správy zdrojového kódu**. Visual Studio vytvoří místní úložiště Git, která obsahuje váš kód projektu.

1. Když Visual Studio zjistí, že projekt spravovat v ovládacích prvcích související Git Git úložiště se zobrazují podél pravém dolním rohu okna Visual Studio. Ovládací prvky zobrazení čekající na potvrzení, změny, název úložiště a větev. Podržte ukazatel nad ovládací prvky zobrazíte další informace.

    ![Další informace se zobrazí, když ukazatele myši na ovládací prvek Git v okně Visual Studio](media/working-with-git-01.png)

1. Při vytváření nového úložiště nebo vyberte některé z ovládacích prvků Git, otevře se Visual Studio **Team Explorer** okno. (Můžete otevřít okno kdykoli bez **zobrazení > Team Explorer** příkazu nabídky.) Okno má tři hlavní panely, které můžete přepínat mezi pomocí rozevíracího seznamu na **Team Explorer** záhlaví. **Synchronizace** podokno, které poskytuje publikování operace, také se zobrazí při výběru ovládacího prvku nabízené (ikonu se šipkou nahoru):

    ![Průzkumník týmových projektů v sadě Visual Studio po vytvoření místní úložiště](media/working-with-git-02.png)

1. Vyberte **změny** (nebo řízení Git s na ikonu tužky) nepotvrzené změny a potvrdit Pokud žádoucí.

    ![Průzkumník týmových projektů v sadě Visual Studio zobrazující nepotvrzené změny](media/working-with-git-03.png)

    Poklikejte na soubor v **změny** seznamu otevřete zobrazení rozdílů pro tento soubor:

    ![Zobrazení rozdílové změny do souboru](media/working-with-git-05.png)

1. Vyberte **větví** (nebo Git ovládací prvek s názvem větev) k ověření větve a provádět operace sloučení a rebase:

    ![Průzkumník týmových projektů v sadě Visual Studio zobrazující větví](media/working-with-git-04.png)

1. Výběr ovládacího prvku Git s názvem úložiště ("CosineWave" v předchozí obrázek), **Team Explorer** ukazuje **připojit** rozhraní, pomocí kterého můžete rychle přepnout do jiného úložiště úplně.

1. Pokud používáte místní úložiště, potvrzené změny přejděte přímo do úložiště. Pokud jste připojení k Vzdálené úložiště, vyberte záhlaví rozevíracího seznamu v **Team Explorer**, zvolte **synchronizace** přepnout do **synchronizace** části a pracovat existuje uvedených příkazů vyžádané a načtení.

## <a name="going-deeper"></a>Budete hlubší

Krátký návod pro vytvoření projektu ze vzdáleného úložiště Git najdete v tématu [rychlý start: klonovat úložiště Python kódu v sadě Visual Studio](quickstart-03-python-in-visual-studio-project-from-repository.md).

Víc komplexní, včetně zpracování ke konfliktům sloučení, kontrola kódu pomocí žádosti o přijetí změn, rebasing a funkce výdej změny mezi větví, na adrese [Začínáme s Git a služby VSTS](/vsts/git/gitquickstart?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json&view=vsts&tabs=visual-studio).

## <a name="tutorial-review"></a>Kurz revize

Blahopřejeme k dokončení tohoto kurzu na Python v sadě Visual Studio. V tomto kurzu naučili jste se postup:

- Vytváření projektů a zobrazit obsah projektu.
- Pomocí editoru kódu a spuštění projektu.
- Použití interaktivních okna nový kód vyvíjet a snadno zkopírovat tento kód do editoru.
- Spusťte program, dokončené v ladicím programu sady Visual Studio.
- Instalovat balíčky a spravovat prostředí Python
- Práce s kódem v úložišti Git

Tady prozkoumejte koncepty a návody, včetně v následujících článcích:

- [Vytvoření rozšíření C++ pro Python](working-with-c-cpp-python-in-visual-studio.md)
- [Publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [Profilace](profiling-python-code-in-visual-studio.md)
- [Testování jednotek](unit-testing-python-in-visual-studio.md)
