---
title: ID pracovního vytížení a komponenta Visual Studio Test Agent 2017
description: Pomocí sady Visual Studio vytížení a komponenta ID spuštění automatizovaných testů a zátěžové testy vzdáleně
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 08/14/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: 55aea29b-1066-4e5a-aa99-fc87d4efb6d5
ms.workload:
- multiple
ms.openlocfilehash: 8b7b10e8039642d7faa025c5360d2731854210d0
ms.sourcegitcommit: 2b1f8e5288582367af2bed20848ba556f146716e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/14/2018
ms.locfileid: "42624260"
---
# <a name="visual-studio-test-agent-2017-component-directory"></a>Visual Studio Test Agent 2017 součástí adresáře

Tabulky v tomto seznamu stránce ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat jako závislost v manifestu VSIX. Všimněte si, že přidáme další součásti vydaných aktualizací sady Visual Studio.

Všimněte si také následující stránka:

* Každá úloha má vlastní oddíl, za nímž následuje Identifikátor pracovního vytížení a tabulku komponent, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **vyžaduje** součásti nainstaluje, když jste si nainstalovali úlohu.
* Pokud budete chtít, můžete nainstalovat také **doporučená** a **volitelné** komponenty.
* Přidali jsme také oddíl, který obsahuje další součásti, které nejsou pod něj nespadá u jakékoli úlohy.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. Určení závislostí naše minimální součástí pomocí tabulek na této stránce. V některých případech to může znamenat, že zadáváte pouze jednu komponentu z pracovního vytížení. V jiných scénářích může znamenat, že zadáte více komponent z jedné úlohy nebo více komponent z více úloh. Další informace najdete v tématu [postupy: migrace projektů rozšíření do sady Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak pomocí těchto identifikátorů najdete v části [pomocí parametrů příkazového řádku instalace sady Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam pracovního vytížení a komponenta ID pro ostatní produkty, naleznete v tématu [funkcí sady Visual Studio 2017 a ID součástí](workload-and-component-ids.md) stránky.

## <a name="test-agent"></a>Test Agent

**ID:** Microsoft.VisualStudio.Workload.TestAgent

**Popis:** podporuje vzdálené spouštění automatizovaných a zátěžových testů

### <a name="components-included-by-this-workload"></a>Pomocí této úlohy zahrnuté komponenty

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.ComponentGroup.TestTools.TestAgent | Základní funkce test agenta | 15.0.27019.1 | Požadováno

## <a name="unaffiliated-components"></a>Nespojená komponenty

Toto jsou komponenty, které nejsou zahrnuty u jakékoli úlohy, ale může vybrat jako jednotlivých komponent.

ID součásti | Název | Version
--- | --- | ---
není k dispozici | není k dispozici | není k dispozici

## <a name="get-support"></a>Získat podporu

V některých případech může něco selže. Pokud se nezdaří instalace aplikace Visual Studio, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud žádný z kroků pro řešení potíží, kontaktujte nás podle živý chat pro pomoc s instalací (jenom v angličtině). Podrobnosti najdete v tématu [stránku podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik dalších možností podpory:

* Může probíhat hlášení problémů s produktem nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu sady Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémů s produktem a najít odpovědi v [komunity vývojářů v aplikaci Visual Studio](https://developercommunity.visualstudio.com/).
* Můžete také Spolupracujte s námi a jinými vývojáři Visual Studio prostřednictvím [konverzace sady Visual Studio v komunitě Gitteru](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účet.)

## <a name="see-also"></a>Viz také:

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
