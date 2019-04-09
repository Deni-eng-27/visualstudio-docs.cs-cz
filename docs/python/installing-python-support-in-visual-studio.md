---
title: Instalace podpory Pythonu
description: Postup instalace nástroje Pythonu pro Visual Studio (PTVS) v sadě Visual Studio 2017, 2015, 2013, 2012 a 2010, včetně možnosti a umístění instalace.
ms.date: 03/13/2019
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: ce4963f753498ff4c43b92b0b59fbfae25a45315
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59366235"
---
# <a name="how-to-install-python-support-in-visual-studio-on-windows"></a>Instalace podpory Pythonu v sadě Visual Studio ve Windows

Instalace podpory Pythonu pro Visual Studio (označované také jako Python Tools for Visual Studio nebo PTVS), postupujte podle pokynů v části, která odpovídá verzi sady Visual Studio:

- [Visual Studio 2017 a Visual Studio 2019](#visual-studio-2017-and-2019)
- [Visual Studio 2015](#visual-studio-2015)
- [Visual Studio 2013 a starší](#visual-studio-2013-and-earlier)

K rychlé otestování podpory Pythonu po provedení kroků instalace, otevřete **interaktivní Python** okno stisknutím kombinace kláves **Alt**+**můžu** a zadáním `2+2`. Pokud nevidíte výstup `4`, spusťte opětovnou kontrolu kroků.

> [!Tip]
> Úlohy Python obsahuje užitečné Cookiecutter rozšíření, která poskytuje grafické uživatelské rozhraní pro zjišťování šablony, zadejte možnosti šablony a vytváření projektů a souborů. Podrobnosti najdete v tématu [použití Cookiecutter](using-python-cookiecutter-templates.md).

> [!Note]
> Podpora Pythonu není v současné době k dispozici v sadě Visual Studio pro Mac, ale je k dispozici na Mac a Linux přes Visual Studio Code. Zobrazit [otázek a odpovědí](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

<a name="visual-studio-2017-and-2019"></a>
## <a name="visual-studio-2019-and-visual-studio-2017"></a>Visual Studio 2019 and Visual Studio 2017

1. Stáhněte a spusťte nejnovější instalační program sady Visual Studio. Pokud máte Visual Studio, už nainstalovali, spusťte instalační program sady Visual Studio, vyberte **změnit** možnost (naleznete v tématu [upravit Visual Studio](../install/modify-visual-studio.md)) a přejděte ke kroku 2.

    > [!div class="nextstepaction"]
    > [Nainstalujte sadu Visual Studio. 2019 Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_gettingstarted)

    >[!Tip]
    > Edice Community je pro jednotlivé vývojáře, školní výuka, vědecký výzkum a vývoj open source. Pro jiné účely, nainstalujte [Visual Studio Professional. 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_gettingstarted) nebo [Visual Studio Enterprise. 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_gettingstarted).

1. Instalační program vám nabídne seznam úloh, které jsou skupiny související možnosti jsou pro vývoj pro konkrétní oblasti. Pro Python, vyberte **vývoj v jazyce Python** pracovního vytížení.

    ![Úloha vývoj v jazyce Python v instalačním programu sady Visual Studio](media/installation-python-workload.png)

    ::: moniker range="vs-2017"
    Volitelné: Pokud pracujete s vědeckým zpracováním dat, zvažte také **pro datové vědy a analytické aplikace** pracovního vytížení. Tato úloha obsahuje podporu pro Python, R, a F# jazyky. Další informace najdete v tématu [pro datové vědy a analytické aplikace úlohy](data-science-and-analytical-applications-workload.md).

    > [!Note]
    > Úlohy Python a datové vědy jsou k dispozici pouze s Visual Studio 2017 verze 15.2 nebo novější.
    ::: moniker-end

    ::: moniker range=">=vs-2019"
    Volitelné: Pokud pracujete s vědeckým zpracováním dat, zvažte také **pro datové vědy a analytické aplikace** pracovního vytížení. Tato úloha obsahuje podporu pro Python a F# jazyky. Další informace najdete v tématu [pro datové vědy a analytické aplikace úlohy](data-science-and-analytical-applications-workload.md).
    ::: moniker-end

1. Na pravé straně instalačního programu zvolte v případě potřeby další možnosti. Přeskočte tento krok přijměte výchozí možnosti.

    ::: moniker range="vs-2017"
    ![Možnosti vývoje Python v instalačním programu sady Visual Studio](media/installation-python-options.png)
    ::: moniker-end

    ::: moniker range=">=vs-2019"
    ![Možnosti vývoje Python v instalačním programu sady Visual Studio 2019](media/installation-python-options-2019.png)
    ::: moniker-end

    | Možnost | Popis |
    | --- | --- |
    | Distribuce Pythonu | Zvolte libovolnou kombinaci dostupných možností, jako je například 32bitové a 64bitové varianty Python 2, Python 3, Miniconda, Anaconda2 a Anaconda3 distribucí, které máte v úmyslu pracovat. Každá obsahuje překladač distribuce, modul runtime a knihovny. Anaconda, je konkrétně open platforma pro datovou vědu, který obsahuje řadu různých předem nainstalované balíčky. (Můžete vrátit do instalačního programu sady Visual Studio kdykoli přidat nebo odebrat distribucí.)  **Poznámka:** Pokud jste nainstalovali distribuce mimo instalačního programu sady Visual Studio, není nutné ke kontrole ekvivalentní možnost. Visual Studio automaticky rozpozná existující instalace Pythonu. Zobrazit [okno The prostředí Pythonu](managing-python-environments-in-visual-studio.md#the-python-environments-window). Navíc pokud novější verzi jazyka Python je k dispozici, než co se zobrazí v instalačním programu, tuto verzi můžete nainstalovat samostatně a Visual Studio zjistí. |
    | **Podpora šablon Cookiecutter** | Nainstaluje Cookiecutter grafického uživatelského rozhraní zjišťovat šablony, zadejte možnosti šablon a vytváření projektů a souborů. Zobrazit [pomocí rozšíření Cookiecutter](using-python-cookiecutter-templates.md). |
    | **Podpora webů v Pythonu** | Nainstaluje nástroje pro vývoj webů, včetně HTML, CSS a JavaScriptu úpravy podporu spolu s šablony projektů s použitím rozhraní Bottle, Flask a Django. Zobrazit [webová šablony projektů v Pythonu](python-web-application-project-templates.md). |
    | **Podpory pro Python IoT** | Podporuje vývoj pro Windows IoT Core pomocí Pythonu. |
    | **Nástroje Pythonu pro nativní vývoj** | Nainstaluje kompilátor jazyka C++ a další komponenty potřebné k vývoji nativních rozšíření pro Python. Zobrazit [vytvoření rozšíření C++ pro Python](working-with-c-cpp-python-in-visual-studio.md). Nainstalovat také **vývoj desktopových aplikací pomocí C++** úlohu pro úplnou podporu C++. |
    | **Základní nástroje pro Azure Cloud Services** | Poskytuje další podporu pro vývojáře cloudových služeb Azure v Pythonu. Zobrazit [projekty Azure cloud service](python-azure-cloud-service-project-template.md). |

1. Po dokončení instalace instalační program poskytuje možnosti, jak změnit, spusťte, opravit nebo odinstalovat Visual Studio. **Změnit** tlačítko se změní na **aktualizace** při aktualizacích sady Visual Studio jsou k dispozici pro všechny nainstalované součásti. ( **Změnit** je pak k dispozici v rozevírací nabídce možnost.) Můžete také spustit Visual Studio a instalační program pro instalaci Windows **Start** nabídky hledáním v "Visual Studio".

    ![Spouštění, úprava, změna nebo odinstalací sady Visual Studio pomocí instalačního programu](media/installation-vs-launch.png)

### <a name="troubleshooting"></a>Poradce při potížích

Pokud narazíte na problémy s instalací nebo spustit jazyk Python v sadě Visual Studio, zkuste následující:

- Určit, zda dochází k ke stejné chybě pomocí rozhraní příkazového řádku Python, který je, spuštěná *python.exe* z příkazového řádku.
- Použití [ **opravit** ](../install/repair-visual-studio.md) možnost v instalačním programu sady Visual Studio.
- Opravte nebo přeinstalujte Python prostřednictvím **nastavení** > **aplikace a funkce** ve Windows.

**Příklad chyba**: Nepodařilo se spustit interaktivní proces: System.ComponentModel.Win32Exception (0x80004005): Neznámá chyba (0xc0000135) na Microsoft.PythonTools.Repl.PythonInteractiveEvaluator.d__43.MoveNext().

## <a name="visual-studio-2015"></a>Visual Studio 2015

1. Spusťte instalační program sady Visual Studio **ovládací panely > programy a funkce**, kde vyberou **Microsoft Visual Studio 2015** a potom **změnu**.

1. V instalačním programu, vyberte **změnit**.

1. Vyberte **programovací jazyky** > **Python Tools for Visual Studio** a potom **Další**:

    ![Možnost PTVS v instalačním programu sady Visual Studio 2015](media/installation-vs2015.png)

1. Po dokončení instalace sady Visual Studio [nainstalujte interpret Pythonu podle vašeho výběru](installing-python-interpreters.md). Visual Studio 2015 podporuje pouze Python 3.5 a starších; novější verze generovat zpráva podobná **nepodporované Python verze 3.6**). Pokud již máte nainstalované překladač a sady Visual Studio nebude automaticky detekovat, naleznete v tématu [ručně identifikovat existující prostředí](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

## <a name="visual-studio-2013-and-earlier"></a>Visual Studio 2013 a starší

1. Nainstalujte odpovídající verzi nástrojů Python Tools for Visual Studio pro vaši verzi sady Visual Studio:

    - Visual Studio 2013: [PTVS 2.2 pro Visual Studio 2013](https://github.com/Microsoft/PTVS/releases/v2.2). **Souboru** > **nový projekt** dialogového okna v sadě Visual Studio 2013 vám poskytne zástupce pro tento proces.
    - Visual Studio 2012: [PTVS 2.1 for Visual Studio 2012](https://pytools.codeplex.com/downloads/get/920478)
    - Visual Studio 2010: [PTVS 2.1 for Visual Studio 2010](https://pytools.codeplex.com/downloads/get/920479)

1. [Nainstalujte interpret Pythonu podle vašeho výběru](installing-python-interpreters.md). Pokud již máte nainstalované překladač a sady Visual Studio nebude automaticky detekovat, naleznete v tématu [ručně identifikovat existující prostředí](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

## <a name="install-locations"></a>Umístění instalace

Ve výchozím nastavení pro všechny uživatele v počítači je nainstalována podpora Pythonu.

Visual Studio 2019 a Visual Studio 2017, je nainstalovaná úloha Pythonu ve *% ProgramFiles (x86) %\Microsoft Visual Studio\\< VS_version >\\< VS_edition > Common7\IDE\Extensions\Microsoft\ Python* kde &lt;VS_version&gt; 2019 nebo 2017 a &lt;VS_edition&gt; je Community, Professional nebo Enterprise.

Pro Visual Studio 2015 a starší instalační cesty jsou následující:

- 32bitová verze:
  - Cesta: *% Program soubory (x86) %\Microsoft Visual Studio \<VS_ver > \Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\\< PTVS_ver >*
  - Umístění registru v rámci cesty: **HKEY_LOCAL_MACHINE\Software\Microsoft\PythonTools\\<VS_ver>\InstallDir**
- 64bitová verze:
  - Cesta: *% Program Files%\Microsoft Visual Studio \<VS_ver > \Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\\< PTVS_ver >*
  - Umístění registru v rámci cesty: **HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\PythonTools\\<VS_ver>\InstallDir**

kde:

- &lt;VS_ver&gt; je:
  - 14.0 pro Visual Studio 2015
  - 12.0 pro Visual Studio 2013
  - 11.0 pro sadu Visual Studio 2012
  - 10.0 pro sadu Visual Studio 2010
- &lt;PTVS_ver&gt; je číslo verze, jako je například 2.2, 2.1, 2.0, 1.5, 1.1 a 1.0.

### <a name="user-specific-installations-15-and-earlier"></a>Uživatelská instalace (1.5 a starší)

Python Tools pro Visual Studio 1.5 a starší povolená instalace pro aktuálního uživatele, v takovém případě cesta instalace je *%LocalAppData%\Microsoft\VisualStudio\\< VS_ver > \Extensions\Microsoft\Python nástroje pro Visual Studio\\< PTVS_ver >* kde &lt;VS_ver&gt; a &lt;PTVS_ver&gt; jsou stejné jako nastavení popsané výše.
