---
title: Visual Studio Test Professional 2017 pracovního vytížení a součást ID
description: Pomocí ID úlohy a součást Visual Studio pro zajištění integrované testovací nástroje Všestranní technici testerům, sada
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 03/05/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: 70c03438-8434-4921-ada0-c172519af431
ms.workload:
- multiple
ms.openlocfilehash: bb6b8f6b4beeb4efa691d53f2c5ac6ab4f9a7cb9
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="visual-studio-test-professional-2017-component-directory"></a>Visual Studio Test Professional 2017 součástí adresáře

V tabulkách na této stránce najdete ID, které můžete použít k instalaci sady Visual Studio pomocí příkazového řádku. Všimněte si, že přidáme další součásti, jako jsme vydání aktualizace pro Visual Studio.

Všimněte si také následující o tuto stránku:

* Každé zatížení má vlastní části, a potom podle ID úlohy a tabulku součásti, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **požadované** součásti se nainstalují při instalaci zatížení. Pokud zvolíte možnost, můžete taky nainstalovat **doporučeno** a **volitelné** součásti.
* Přidali jsme také oddíl, který uvádí další součásti, které nejsou spojit s jakoukoli úlohu.

Další informace o tom, jak používat tyto identifikátory najdete v tématu [pomocí parametrů příkazového řádku pro instalaci Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam úloh a ID součástí pro ostatní produkty, naleznete v části [zatížení 2017 Visual Studio a ID součástí](workload-and-component-ids.md) stránky.

## <a name="test-professional"></a>Test Professional

**ID:** Microsoft.VisualStudio.Workload.TestProfessional

**Popis:** Test Professional poskytuje integrované testovací nástroje zaměřený na Všestranní technici testerů, které pomůžou je jednotka jejich testování potřeb napříč celý životní cyklus testování.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Feedback Client | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.6.27406.0 | Požadováno

## <a name="unaffiliated-components"></a>Nezávislou na komponenty

Toto jsou součásti, které nejsou součástí žádné úlohy, ale může být vybraný jako jednotlivé součásti.

ID součásti | Název | Version
--- | --- | ---
není k dispozici | není k dispozici | není k dispozici

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
