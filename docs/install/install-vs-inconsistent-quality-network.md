---
title: "Nainstalujte na malou šířkou pásma nebo nespolehlivé mezi sítě v prostředích | Microsoft Docs"
description: "Popisuje, jak funguje instalační program sady Visual Studio v podmínkách nespolehlivé mezi sítě a vysvětluje, jak ke stažení instalačních souborů před zahájením instalace."
ms.date: 08/30/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 44DB1998-68CD-4560-870A-EE5B993DCF6E
author: timsneath
ms.author: tims
manager: ghogen
ms.openlocfilehash: 57665c39c875b57a1e90c4f57de68f069823cc86
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Nainstalovat Visual Studio 2017 na malou šířkou pásma nebo nespolehlivé mezi sítě v prostředích

Doporučujeme vám, že zkusíte webovou Instalační službu sady Visual Studio&mdash;myslíme si, naleznete je kvalitní většině situací.

 > [!div class="button"]
 > [Stáhněte si Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Ale pokud vaše připojení k Internetu je k dispozici nebo nespolehlivé, můžete příkazového řádku k vytvoření místní mezipaměti souborů, které potřebujete k dokončení instalace v režimu offline. Tady je způsob.

> [!NOTE]
> Pokud jste správce organizace, který chce provést nasazení sady Visual Studio 2017 k síti klientské pracovní stanice, které jsou bránou firewall z Internetu, najdete v našich [vytvořit sítě instalaci sady Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) a [Zvláštní požadavky pro instalaci sady Visual Studio v režimu offline](../install/install-visual-studio-in-offline-environment.md) stránky.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>Krok 1 – stažení zaváděcího nástroje Visual Studio

Spusťte stažením zaváděcího nástroje Visual Studio pro vaši zvolenou edice sady Visual Studio.

Instalační soubor&mdash;nebo být konkrétnější, soubor zaváděcího nástroje&mdash;bude odpovídat nebo podobný jednu z následujících.

| Edice                    | Soubor                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>Krok 2 – Vytvoření mezipaměti místní instalace

Musí mít připojení k Internetu k dokončení tohoto kroku. Pokud chcete vytvořit místní rozložení, otevřete příkazový řádek a použijte jednu z následujících příkladech příkazů: Příklady zde předpokládají, že používáte edice Community sady Visual Studio; Upravte příkaz podle potřeby vaší verze.

- Webové rozhraní .NET a vývoj aplikací .NET spusťte:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- Pro stolní počítače rozhraní .NET a vývoj pro Office spusťte příkaz:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- Vývoj aplikací C++ spusťte příkaz:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Chcete-li vytvořit úplný místní rozložení se všemi funkcemi (bude to trvat dlouhou dobu&mdash;máme _mnoha_ funkcí!) spusťte:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

Pokud chcete nainstalovat jiný jazyk než anglický, změňte `en-US` pro národní prostředí ze seznamu v dolní části této stránky. Použít [seznam součástí a úlohy zůstaly dostupné](workload-and-component-ids.md) k dalšímu přizpůsobení instalace mezipaměti podle potřeby.

> [!IMPORTANT]
> Dokončení rozložení Visual Studio 2017 vyžaduje alespoň 35 GB místa na disku a může trvat nějakou dobu ke stažení. V tématu [používání parametrů příkazového řádku pro instalaci Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) informace o tom, jak vytvořit rozložení s pouze komponenty chcete nainstalovat.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>Krok 3: instalace sady Visual Studio z místní mezipaměti

> [!TIP]
> Když spustíte z mezipaměti místní instalace, instalační program používá místní verze každého z těchto souborů. Ale pokud vyberete součásti během instalace, které nejsou v mezipaměti, budeme pokoušet stáhnout z Internetu.

K zajištění instalovat pouze soubory, které jste stáhli, použijte stejné možnosti příkazového řádku, které jste použili k vytvoření mezipaměti rozložení. Například pokud jste vytvořili mezipaměti rozložení pomocí následujícího příkazu:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

Použijte tento příkaz ke spuštění instalace:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

  > [!NOTE]
  > Pokud dojde k chybě, že podpis je neplatný, je nutné nainstalovat aktualizované certifikáty. Otevřete složku Certifikáty v mezipaměti v režimu offline. Dvakrát klikněte na každý ze souborů certifikátu a potom klikněte pomocí Průvodce správce certifikátů. Pokud se zobrazí výzva k zadání hesla, ponechte prázdné.

## <a name="list-of-language-locales"></a>Seznam národní prostředí

| **Národní prostředí** | **Jazyk** |
| ----------------------- | --------------- |
| cs-CZ | Čeština |
| de-DE | Němčina |
| en US | Angličtina |
| ES-ES | Španělština |
| fr-FR | Francouzština |
| IT-IT | Italština |
| ja-JP | Japonština |
| ko-KR | Korejština |
| pl-PL | Polština |
| pt-BR | Portugalština – Brazílie |
| ru-RU | Ruština |
| tr-TR | Turečtina |
| zh-CN | -Čínština, zjednodušená čínština |
| zh-TW. | Tradiční čínština – |

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Instalaci sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
