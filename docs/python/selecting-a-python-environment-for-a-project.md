---
title: Výběr interpretu Pythonu a prostředí pro projekt
description: Jak přiřadit prostředí Pythonu pro projekt sady Visual Studio, a navíc pokyny k vytvoření virtuálních prostředí.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 63fa8e83fd94be5307541ca7e070d47c8fa04488
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586375"
---
# <a name="how-to-assign-which-python-environment-is-used-for-a-project"></a>Jak přiřadit prostředí Pythonu, ve kterém se používá pro projekt

Veškerý kód v projektu Pythonu běží v kontextu konkrétní prostředí. Visual Studio také používá pro ladění, import a dokončování členů, kontrola syntaxe a další úlohy, které vyžadují prostředí daného prostředí.

Všechny nové projekty Pythonu v sadě Visual Studio jsou původně nakonfigurovány pro použití výchozí globální prostředí, které se zobrazí pod **prostředí Pythonu** uzel v **Průzkumníka řešení**:

![Globální výchozí nastavení prostředí Pythonu zobrazovat v Průzkumníkovi řešení](media/environments-project.png)

Chcete-li změnit prostředí pro projekt, klikněte pravým tlačítkem myši **prostředí Pythonu** uzel a vyberte možnost **přidat nebo odebrat prostředí Pythonu**. Ze zobrazeného seznamu, který obsahuje globální, virtuální, a prostředí conda, vyberte všechny ty, které se mají zobrazit v části **prostředí Pythonu** uzlu:

![Dialogové okno Přidat nebo odebrat prostředí Pythonu](media/environments-add-remove.png)

Jakmile vyberete **OK**, všechny vybrané prostředí se zobrazí v rámci **prostředí Pythonu** uzlu. Aktuálně aktivovaná prostředí se zobrazí tučně:

![Více prostředí Pythonu zobrazovat v Průzkumníkovi řešení](media/environments-project-multiple.png)

Aktivujte rychle jiné prostředí, klikněte pravým tlačítkem na tento název prostředí a vyberte **aktivovat prostředí**. Podle vašeho výběru se uloží s projektem a toto prostředí se aktivuje vždy, když otevřete projekt v budoucnu. Pokud zrušíte všechny možnosti v **přidat nebo odebrat prostředí Pythonu** dialogovém okně Visual Studio aktivuje globální výchozí prostředí.

V místní nabídce **prostředí Pythonu** uzel poskytuje také další příkazy:

| Příkaz | Popis |
| --- | --- |
| **Přidat virtuální prostředí** | Spustí proces vytváření nové virtuální prostředí v projektu. Zobrazit [vytvořit virtuální prostředí](#create-a-virtual-environment). |
| **Přidat existující virtuální prostředí** | Výzva k výběru složky obsahující virtuální prostředí a přidá ji do seznamu **prostředí Pythonu**, ale ne aktivovat. Zobrazit [aktivovat existující virtuální prostředí](#activate-an-existing-virtual-environment). |
| **Vytvořit prostředí Conda** | Přepne **prostředí Pythonu** *okno* ve kterém zadáte název prostředí a jeho základní překladač. |

## <a name="use-virtual-environments"></a>Použití virtuálního prostředí

Virtuální prostředí již není jedinečnou kombinaci konkrétní interpret Pythonu a konkrétní sadu knihoven, které se liší od jiných prostředí conda a globální. Virtuální prostředí je specifické pro projekt a je udržován ve složce projektu. Tato složka obsahuje knihovny nainstalované prostředí společně s *pyvenv.cfg* soubor, který určuje cestu k prostředí *základní interpret* jinde v systému souborů. (To znamená, do virtuálního prostředí neobsahuje kopii překladač pouze odkaz na něj.) 

Výhoda použití virtuální prostředí je, že při vývoji projektu v čase, virtuální prostředí vždy odráží přesné závislosti projektu. (Sdílené globální prostředí, na druhé straně obsahuje libovolný počet knihoven, zda je použijete v projektu nebo ne). Potom můžete snadno vytvořit *souboru requirements.txt* souboru z virtuálního prostředí, které se pak použije k opětovné instalaci těchto závislostí na jiném počítači vývojové nebo produkční prostředí. Další informace najdete v tématu [spravovat vyžadované balíčky pomocí souboru requirements.txt](managing-required-packages-with-requirements-txt.md).

Když otevřete projekt v sadě Visual Studio, který obsahuje *souboru requirements.txt* souboru, Visual Studio automaticky nabízí možnost znovu vytvořit virtuální prostředí. Na počítačích, kde není nainstalovaná sada Visual Studio, například Azure App Service, můžete použít `pip install -r requirements.txt` obnovení balíčků (Tento proces je popsaný na [Správa Pythonu ve službě Azure App Service](managing-python-on-azure-app-service.md)).

Protože virtuální prostředí obsahuje pevně zakódované cesty k základní interpret, a proto můžete znovu vytvořit prostředí pomocí *souboru requirements.txt*, obvykle vynechat celé virtuální prostředí složky ze správy zdrojového kódu.

Následující části popisují postup aktivace služby existující virtuální prostředí v projektu a jak vytvořit nové virtuální prostředí.

V sadě Visual Studio, můžete aktivovat do virtuálního prostředí pro projekt jako u všech ostatních prostřednictvím **prostředí Pythonu** uzel v **Průzkumníka řešení**.

Když do projektu se přidá do virtuálního prostředí, zobrazí se v **prostředí Pythonu** okna. Můžete potom si ji můžou aktivovat stejně jako jakékoli jiné prostředí, a můžete spravovat své balíčky.

### <a name="create-a-virtual-environment"></a>Vytvoření virtuálního prostředí

Přímo ze sady Visual Studio můžete vytvořit nové virtuální prostředí následujícím způsobem:

1. Klikněte pravým tlačítkem na **prostředí Pythonu** v **Průzkumníka řešení** a vyberte **přidat virtuální prostředí**, který se zobrazí následující dialogové okno:

    ![Vytváří se virtuální prostředí](media/environments-add-virtual-1.png)

1. V **umístění virtuálního prostředí** pole, zadejte cestu pro virtuální prostředí. Pokud zadáte pouze název, vytvoření virtuálního prostředí v rámci aktuálního projektu v podsložce s názvem.

1. Jako základní překladač vyberte prostředí a vyberte **vytvořit**. Visual Studio zobrazí indikátor průběhu, zatímco prostředí nakonfiguruje a stáhne všechny potřebné balíčky. V tomto okamžiku virtuální prostředí se zobrazí v **prostředí Pythonu** okno pro projekt.

1. Ve výchozím nastavení není aktivován virtuální prostředí. Chcete-li aktivovat pro projekt, pravým tlačítkem myši a vyberte **aktivovat prostředí**.

> [!Note]
> Pokud Určuje cestu k umístění existující virtuální prostředí, sada Visual Studio automaticky zjistí základní interpret (pomocí *orig prefix.txt* souboru v prostředí *lib* adresáře) a změny **vytvořit** tlačítko **přidat**.
>
> Pokud *souboru requirements.txt* soubor existuje, když přidáte do virtuálního prostředí **přidat virtuální prostředí** dialogového okna se zobrazí možnost automaticky, nainstalujte balíčky usnadňuje znovu vytvořit prostředí v jiném počítači:
>
> ![Vytvořit virtuální prostředí pomocí souboru requirements.txt](media/environments-requirements-txt.png)
>
> V obou případech výsledek je stejný, jako jste použili **přidat existující virtuální prostředí** příkazu.

### <a name="activate-an-existing-virtual-environment"></a>Aktivovat existující virtuální prostředí

Pokud už máte vytvořený virtuální prostředí jinde, můžete si ji můžou aktivovat pro projekt následujícím způsobem:

1. Klikněte pravým tlačítkem na **prostředí Pythonu** v **Průzkumníka řešení** a vyberte **přidat existující virtuální prostředí**.

1. V **Procházet** zobrazeném dialogovém okně přejděte a vyberte složku, která obsahuje virtuální prostředí, a vyberte **OK**. Pokud sada Visual Studio zjistí *souboru requirements.txt* soubor v daném prostředí dotazem, zda k instalaci těchto balíčků.

1. Po chvíli se virtuální prostředí se zobrazí v části **prostředí Pythonu** uzel v **Průzkumníka řešení**. Ve výchozím nastavení není aktivován virtuální prostředí, takže pravým tlačítkem myši a vyberte **aktivovat prostředí**.

### <a name="remove-a-virtual-environment"></a>Odebrat virtuální prostředí

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na virtuální prostředí a vyberte **odebrat**.

1. Visual Studio zeptá, jestli se má odebrat nebo odstranit virtuální prostředí. Výběr **odebrat** udělá jej nedostupným do projektu, ale ponechá ho v systému souborů. Výběr **odstranit** odebere prostředí z projektu i odstraní ze systému souborů. Základní interpret je poškozena.

## <a name="view-installed-packages"></a>Zobrazit nainstalované balíčky

V Průzkumníku řešení rozbalte uzel pro jakékoli konkrétní prostředí rychle zobrazit balíčky, které jsou nainstalované ve prostředí (to znamená, že můžete importovat a používat tyto balíčky v kódu při aktivním prostředí):

![Balíčky Pythonu pro prostředí v Průzkumníku řešení](media/environments-installed-packages.png)

Chcete-li nainstalovat nové balíčky, klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Pythonu** přepnout na **balíčky** kartu **prostředí Pythonu** okna. Zadejte hledání termín (obvykle název balíčku) a Visual Studio zobrazí odpovídající balíčky.

V sadě Visual Studio, se stáhnou balíčky (a závislosti) z [indexu balíčků Pythonu (PyPI)](https://pypi.org), kde můžete také vyhledat dostupné balíčky. Stavový řádek sady Visual Studio a okno výstup zobrazí informace o instalaci. Chcete-li odinstalovat balíček, pravým tlačítkem myši a vyberte **odebrat**.

Mějte na paměti, že zobrazené položky vždy nemusí být přesné a instalace a odinstalace nemusí být spolehlivé nebo nejsou k dispozici. Visual Studio pomocí Správce balíčků pip, pokud je k dispozici a stáhne a nainstaluje ho v případě potřeby. Visual Studio můžete také použít Správce balíčků easy_install. Balíčky nainstalované pomocí `pip` nebo `easy_install` z příkazového řádku se také zobrazují.

Všimněte si také, Visual Studio nepodporuje v současné době použití `conda` nainstalovat balíčky prostředí conda. Použití `conda` příkazovém řádku místo.

> [!Tip]
> Běžné situace, ve kterém se nepodařilo nainstalovat balíček pip je, když balíček obsahuje zdrojový kód pro nativní součásti v  *\*.pyd* soubory. Bez požadovanou verzi sady Visual Studio nainstalované nejde zkompilovat pip tyto komponenty. Chybová zpráva zobrazená v této situaci je **Chyba: nepovedlo se najít vcvarsall.bat**. `easy_install` často je možné stáhnout předem zkompilované binární soubory, a můžete si stáhnout vhodný kompilátoru pro starší verze jazyka Python z [ http://aka.ms/VCPython27 ](http://aka.ms/VCPython27). Další podrobnosti najdete v tématu [jak zacházet s usnadnit práci z "nelze najít vcvarsallbat"](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) na Pythonu blogu týmu nástroje.

## <a name="see-also"></a>Viz také:

- [Správa prostředí Pythonu v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Pythonu](python-environments-window-tab-reference.md)