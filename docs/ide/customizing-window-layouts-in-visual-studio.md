---
title: Přizpůsobení rozložení oken v sadě Visual Studio
ms.date: 01/23/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.windows
- vs.environment
helpviewer_keywords:
- windows [Visual Studio], managing
- custom window configurations
- layout [Visual Studio], window management
- document windows [Visual Studio]
- interface modes
- AutoHide windows
- MDI, window interface modes
- multiple monitors
- Tabbed Document mode
- debug mode
- custom layouts
ms.assetid: 7517ff13-76de-4ecf-9c1b-eb9b7ff4d718
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62fa251eac1546b0d5588dfc4dc43bead725bf81
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746842"
---
# <a name="customize-window-layouts-in-visual-studio"></a>Přizpůsobení rozložení oken v sadě Visual Studio

V sadě Visual Studio můžete přizpůsobit pozici, velikost a chování systému windows pro vytvoření rozložení oken, která nejlépe pro různé pracovní postupy pro vývoj. Při přizpůsobování rozložení IDE ho pamatuje. Například, pokud změníte ukotvení umístění **Průzkumníku řešení** a pak zavřete Visual Studio, při příštím spuštění se i v případě, že pracujete v jiném počítači, **Průzkumníku řešení** bude ukotveno v tomto stejné umístění. Můžete také pojmenujte vlastní rozložení a uložit jej a potom přepínat mezi rozložení pomocí jednoho příkazu. Například můžete vytvořit rozložení pro úpravy a druhou pro ladění a přepínat mezi nimi pomocí **okno** > **použít rozložení okna** příkazu nabídky.

## <a name="kinds-of-windows"></a>Druhy oken

### <a name="tool-and-document-windows"></a>Nástroje a okna dokumentu

Prostředí IDE má dva základní typy, *nástroj windows* a *dokumentu windows*. Okna nástrojů zahrnují **Průzkumníku řešení**, **Průzkumníka serveru**, **výstup – okno**, **seznam chyb**, návrháři, ladicího programu , a tak dále. Okna dokumentu obsahovat soubory zdrojového kódu, libovolný textové soubory, konfigurační soubory a tak dále. Nástroje systému windows můžete po změně velikosti a přetažením pomocí jejich záhlaví. Okna dokumentu můžete přetáhnout podle jejich kartě. Klikněte pravým tlačítkem myši na kartu nebo záhlaví panelu nastavit další možnosti v okně.

**Okno** nabídce jsou možnosti pro ukotvení, číslo s plovoucí čárkou a skrytí windows v prostředí IDE. Klikněte pravým tlačítkem na řádku okna kartě nebo název zobrazíte další možnosti pro tento konkrétní okno. Najednou můžete zobrazit více než jednu instanci určité nástroje systému windows. Například můžete zobrazit více než jeden okno prohlížeče a další instance některých nástroje systému windows můžete vytvořit tak, že zvolíte **nové okno** na **okno** nabídky.

### <a name="preview-tab-document-windows"></a>Karta náhled (dokument windows)

V **Preview** kartě, můžete zobrazit soubory v editoru bez jejich otevření. Náhled soubory můžete zobrazit a vybrat je v **Průzkumníku řešení**, během ladění, když jste do souborů, s krokem **přechod na definici**, a při procházení výsledky hledání. Soubory Preview se zobrazí na kartě na pravé straně dobře dokumentu karty. Soubor se otevře pro úpravy, pokud ji upravit nebo zvolte **otevřete**.

### <a name="tab-groups"></a>Karta skupiny

Karta skupiny rozšířit možnost správy omezené prostoru při práci s minimálně dva otevřené dokumenty v prostředí IDE. Můžete uspořádat více dokumentů windows a nástroj windows do skupin buď svislé nebo vodorovné kartě a náhodně dokumenty z jedné karty skupiny do jiného.

### <a name="split-windows"></a>Rozdělení oken

Pokud máte k zobrazení nebo upravte dvěma umístěními najednou v dokumentu, můžete rozdělit windows. Rozdělení na dva oddíly nezávisle posouvání dokumentu, klikněte na tlačítko **rozdělení** na **okno** nabídky. Klikněte na tlačítko **odebrat rozdělení** na **okno** nabídky k obnovení jednoho zobrazení.

### <a name="toolbars"></a>Panely nástrojů

Panely nástrojů mohou být uspořádány tak, že přetáhnete nebo pomocí **přizpůsobit** dialogové okno. Další informace o tom, jak umístit a přizpůsobení panelů nástrojů najdete v tématu [postupy: přizpůsobení nabídek a panelů nástrojů](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md).

## <a name="arrange-and-dock-windows"></a>Rozvržení a dokování oken

Může být okna dokumentu nebo okno nástroje *ukotveného*, tak, aby měl pozice a velikosti v rámci rámce okna IDE nebo číslo s plovoucí čárkou jako samostatné okno nezávislé rozhraní IDE. Nástroje systému windows můžete kdekoli ukotven uvnitř rámečku IDE; Některé nástroje systému windows lze ukotvit jako záložkách windows v rámci editor. Okna dokumentu lze ukotvit v rámci editoru a může být připnutý k jejich aktuální pozici v pořadí. Více oken můžete ukotvit float společně v *raft* přes nebo mimo prostředí IDE. Nástroje systému windows můžete také skrytý nebo minimalizovat.

Windows můžete uspořádat následujícími způsoby:

-   Dobře připnete okna dokumentu nalevo od kartě.

-   Karta ukotvení windows úpravy rámečku.

-   Okna nástrojů ukotvení na okraj rámce v prostředí IDE.

-   Float dokument nebo nástroj windows přes nebo mimo prostředí IDE.

-   Skryjte okna nástrojů okraji rozhraní IDE.

-   Zobrazení oken na různých monitorování.

-   Umístění okno obnovte výchozí rozložení nebo uložené vlastní rozložení.

Nástroje a okna dokumentu mohou být uspořádány tak, že přetáhnete pomocí příkazů v **okno** nabídce a kliknutím pravým tlačítkem myši na záhlaví okna uspořádat.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

### <a name="dock-windows"></a>Dokování oken

Když klikněte na tlačítko a přetáhněte ji na záhlaví okna nástroje nebo na kartě okna dokumentu, zobrazí se Průvodce kosočtverec. Během operace přetažení Pokud se ukazatel myši nad jednu z šipky v kosočtverec, podbarvené oblasti se objeví který ukazuje, kde bude okno ukotveno, pokud teď uvolnění tlačítka myši.

Chcete-li okno lze ukotvit bez uchycení na místo, zvolte **Ctrl** klíče při přetahování okna.

Chcete-li vrátit do jeho nejnovější ukotveného umístění okno nástroje nebo okna dokumentu, stiskněte **Ctrl** při dvakrát kliknete na záhlaví okna nebo karty okna.

Následující obrázek znázorňuje kosočtverec Průvodce pro dokument windows, které lze ukotvit pouze v rámci úpravy:

![Kosočtverec Průvodce okna dokumentu](../ide/media/documentwindowguidediamonds.png)

Nástroje systému windows může mít zapínání na jedné straně rámce v prostředí IDE nebo v rámci úpravy. Při přetahování okno nástroje do jiného umístění umožňují snadno znovu ukotvení okno se zobrazí Průvodce kosočtverec.

Průvodce kosočtverec pro nástroje systému windows

![Nástroj okno Průvodce diamanty](../ide/media/vs10guidediamond.png)

Následující obrázek znázorňuje **Průzkumníku řešení** se ukotven do nového umístění, které se zobrazí modré podbarvené oblasti:

![Ukotvení Průzkumníku řešení v nové místo](../ide/media/vs2015_dock_diamond.png)

### <a name="close-and-auto-hide-tool-windows"></a>Zavřete a automaticky skrýt okna nástrojů

Kliknutím můžete zavřít okno nástroje **X** v pravém horním rohu stránky na záhlaví; Pokud chcete znovu otevřít okno, použijte jeho klávesnice zástupce nebo příkazu nabídky. Nástroje systému windows podporují funkci s názvem *automaticky skrýt*, což způsobí, že okno na snímek stranou použijete jiné časové období. Pokud je okno skrytý automaticky, jeho název se zobrazí na kartě na hranici rozhraní IDE. Okno znovu použít, přejděte na na kartě, aby snímky okno zpět do zobrazení.

![Skrýt automaticky](../ide/media/vs2015_auto_hide.png)

> [!NOTE]
> Chcete-li nastavit, jestli chcete automaticky skrýt funguje na nástroj windows samostatně nebo jako ukotveného skupin, zaškrtněte nebo zrušte **automaticky skrýt tlačítko ovlivňuje pouze aktivní nástroj windows** v **možnosti** dialogové okno. Další informace najdete v tématu [Obecné, prostředí, dialogové okno Možnosti](../ide/reference/general-environment-options-dialog-box.md).

> [!NOTE]
> Okna nástrojů, které mají automaticky skrýt povoleno může dočasně Vysuňte do zobrazení, pokud má okno fokus. Chcete-li skrýt okna znovu, vyberte položku mimo aktuální okno. Pokud okno ztratí fokus, snímky zpět mimo zobrazení.

### <a name="specifying-a-second-monitor"></a>Určení druhém monitoru

Pokud máte druhém monitoru a váš operační systém podporuje, můžete vybrat, které monitorování zobrazí okno. Můžete dokonce seskupit více oken v *vorech* na jiných monitorech.

> [!TIP]
> Můžete vytvořit více instancí **Průzkumníku řešení** a přesuňte je do jiné monitorování. Klikněte pravým tlačítkem na okno a zvolte **nové zobrazení Průzkumníka řešení**. Všechny systémy windows můžete vrátit zpět na původní monitorování dvojitým kliknutím na soubor při výběru **Ctrl** klíč.

### <a name="reset-name-and-switch-between-window-layouts"></a>Resetování, název a přepínání mezi rozložení oken

Můžete se vrátit IDE původní rozložení okna nastavení kolekce pomocí **resetovat rozložení okna** příkaz. Když spustíte tento příkaz, provedou se tyto akce:

-   Všechny systémy windows přesunou na výchozí pozici.

-   Windows, které jsou v výchozího rozložení okna jsou uzavřeny.

-   Windows, které jsou otevřeny v výchozího rozložení okna jsou otevřené.

### <a name="create-and-save-custom-layouts"></a>Vytvořte a uložte vlastní rozložení

Visual Studio můžete uložit až 10 vlastního rozložení oken a rychlé přepínání mezi nimi. Následující kroky ukazují, jak vytvořit, uložit, vyvolání a spravovat vlastní rozložení, které budou využívat více monitorů s ukotveného a plovoucí nástroje systému windows.

Nejprve vytvořte testovací řešení, které má dva projekty každé rozložení optimální.

#### <a name="create-a-ui-project-and-customize-the-layout"></a>Vytvoření projektu uživatelského rozhraní a přizpůsobení rozložení

1.  V **nový projekt** dialogové okno, vytvoření **WPF plochy aplikace v C#** a volání se vám líbí. Předstírají, že je projekt kde jsme budete pracovat v uživatelském rozhraní, tak chcete maximalizovat místa pro návrháře okno a stranou přesunout jiné nástroje systému windows.

2.  Pokud máte více monitorů, pull **Průzkumníku řešení** okno a **vlastnosti** okno přes na druhém monitoru. Na jednom monitorování systému zavřete všechna okna s výjimkou návrháře.

3.  Stiskněte klávesu **Ctrl + Alt + X** zobrazíte **sada nástrojů**. Pokud je ukotveno okna, přetáhněte jej ji uvolnit někde kam chcete umístit je na buď monitorování.

4.  Stiskněte klávesu **F5** Visual Studio uvést do režimu ladění. Upravit jeho umístění **automobily**, **zásobníkem volání** a **výstup** ladění způsob, jakým je chcete v systému windows. Použije se rozložení, který se chystáte vytvořit pro úpravy režimu i režimu ladění.

5.  Pokud vaše rozložení v ladění režimu i režimu úprav jsou jejich, z hlavní nabídky zvolte **okno** > **uložit rozložení okna**. Volání toto rozložení "Designer".

     Všimněte si, že nové rozložení je přiřazený další klávesovou zkratku ze seznamu vyhrazené **Ctrl** + **Alt** + **1... 0**.

#### <a name="create-a-database-project-and-layout"></a>Vytvořte projekt databáze a rozložení

1.  Přidejte nový **databáze systému SQL Server** projektu k řešení.

2.  Klikněte pravým tlačítkem na nový projekt v **Průzkumníku řešení** a zvolte **zobrazení v nástroji Object Explorer**. Zobrazí se **Průzkumník objektů systému SQL Server** okno, které vám umožňuje přístup k tabulkám, zobrazení a dalších objektů v databázi. Můžete buď float toto okno nebo necháte ukotven. Upravte způsob, jakým chcete je jiné nástroje systému windows. Pro přidání realism můžete přidat samotné databázi, ale není nutné v tomto návodu.

3.  Pokud vaše rozložení je, jak chcete, z hlavní nabídky zvolte **okno** > **uložit rozložení okna**. Volání toto rozložení "DB projektu." (Jsme nebude zabývat rozložení režim ladění pro tento projekt.)

#### <a name="switch-between-the-layouts"></a>Přepínání mezi rozložení

Přepínat mezi rozložením, používání klávesových zkratek, nebo z hlavní nabídky zvolte **okno** > **použít rozložení okna**.

![Použít nabídku rozložení okna](../ide/media/vs2015_applywindowlayout.png)

Po použití rozložení uživatelského rozhraní, Všimněte si, jak rozložení se zachová, i v režimu úprav i v režimu ladění.

Pokud máte doma instalace v práci a jednoho monitoru přenosného počítače s více monitorování, můžete vytvořit rozložení, které jsou optimalizované pro každý počítač.

> [!NOTE]
> Pokud použijete rozložení více monitorování v jedné monitorování systému, bude plovoucí windows, které jste umístili na druhém monitoru skrytá za okno sady Visual Studio. Tyto windows můžete přenést do popředí stisknutím **Alt + Tab**. Pokud později otevřete Visual Studio s více monitory, můžete obnovit systému windows na zadané pozici znovu použitím rozložení.

#### <a name="manage-and-roam-your-layouts"></a>Spravovat a mohla používat vaše rozložení

Můžete odebrat, přejmenovat nebo změnit jeho pořadí vlastní rozložení výběrem **okno** > **spravovat rozložení oken**. Pokud přesunete rozložení, vazbu klíče je automaticky upravována tak, aby odrážely novou pozici v seznamu. Vazby nelze jinak upravit, a proto můžete uložit maximálně 10 rozložení najednou.

![Spravovat rozložení oken](../ide/media/managewindowlayouts.png)

Abyste nezapomněli které klávesnice zkratka přiřazená k jaké rozložení, zvolte **okno** > **použít rozložení okna**.

Tyto rozložení automaticky roaming mezi edice sady Visual Studio a taky mezi instancemi Blend na samostatné počítače a z jakékoli edice Express k jiné organizaci Express. Rozložení však není přenášet mezi Visual Studio, Blend a Express.

## <a name="see-also"></a>Viz také:

- [Postupy: pohyb v integrovaném vývojovém prostředí](../ide/how-to-move-around-in-the-visual-studio-ide.md)