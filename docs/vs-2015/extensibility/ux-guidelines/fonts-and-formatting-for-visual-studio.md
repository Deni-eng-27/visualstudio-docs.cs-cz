---
title: Písma a formátování
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: c3c3df69-83b4-4fd0-b5b1-e18c33f39376
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ede8844b34473e1c900bd6af040cac99ceee1514
ms.sourcegitcommit: 3154387056160bf4c36ac8717a7fdc0cd9faf3f9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2020
ms.locfileid: "78409911"
---
# <a name="fonts-and-formatting-for-visual-studio"></a>Písma a formátování pro Visual Studio
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

## <a name="BKMK_TheEnvironmentFont"></a>Písmo prostředí
 Všechna písma v sadě Visual Studio musí být vystavené pro uživatele pro přizpůsobení. To se primárně provádí pomocí stránky **písma a barvy** v dialogovém okně **Nástroje > Možnosti** . Jsou tři hlavní kategorie nastavení písma:

- **Písmo prostředí** – primární písmo pro integrované vývojové prostředí (IDE), které se používá pro všechny prvky rozhraní, včetně dialogových oken, nabídek, oken nástrojů a oken dokumentů. Ve výchozím nastavení písmo prostředí je vázán na systémové písmo, které se zobrazí jako 9 pt Segoe UI v aktuálních verzích Windows. Pomocí jednoho písma pro všechny prvky rozhraní pomáhá zajistit vzhled písma konzistentní v celém rozhraní IDE.

- **Textový editor** – prvky, které jsou na kódu a další textové editory, lze přizpůsobit na stránce textový editor v **nabídce Nástroje > Možnosti**.

- **Konkrétní kolekce** – okna návrháře, která nabízí vlastní nastavení prvků rozhraní, mohou vystavit písma specifická pro svoji návrhovou plochu na jejich vlastní stránce nastavení v části **Nástroje > Možnosti**.

### <a name="editor-font-customization-and-resizing"></a>Vlastní nastavení písma editoru a změnu velikosti
 Uživatelé budou často zvětšení nebo zvětšení velikosti a/nebo barvu textu v editoru podle jejich priority, nezávislé na obecné uživatelského rozhraní. Písmo prostředí, protože se používají u elementů, které se zobrazují v rámci nebo jako součást editoru nebo návrháře je důležité si uvědomit očekávané chování, pokud jeden z těchto písmo klasifikace se změnilo.

 Při vytváření prvků uživatelského rozhraní, které se zobrazí v editoru, ale nejsou součástí *obsahu*, je důležité použít písmo prostředí a nikoli text písma, aby se prvky měnily předvídatelným způsobem.

1. V editoru kódu text velikost s nastavením písmo textu kódu a reagovat na úroveň přiblížení editoru textu.

2. Všechny ostatní prvky rozhraní by měl být svázané písma nastavení prostředí a reagovat na všechny globální změny v prostředí. To zahrnuje (ale není omezena pouze na):

    - Text v kontextové nabídky

    - Editor panelu hledání textu v dalších úprav editoru, jako je text nabídky návrhy, rychlé a přejděte do podokna

    - Text popisku v dialogových oknech, jako je například hledání v souborech nebo Refaktorujte

### <a name="accessing-the-environment-font"></a>Přístup k prostředí písma
 V nativním kódu nebo v kódu WinForms je možné k písma prostředí přistupovat voláním metody **IUIHostLocale:: GetDialogFont** po dotazování rozhraní ze služby SID_SUIHostLocale.

 Pro Windows Presentation Foundation (WPF) odvodíte třídu vašeho dialogového okna z třídy **DialogWindow** Shell namísto třídy **okna** WPF.

 V XAML kód vypadá například takto:

```
<ui:DialogWindow
    x:Class"MyNameSpace.MyWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:s="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:ui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"
    ShowInTaskbar="False"
    WindowStartupLocation="CenterOwner"
    Title="My Dialog">
</ui:DialogWindow>

code behind:

internal partial class WebConfigModificationWindow : DialogWindow
{
}

```

 (Nahraďte `Microsoft.VisualStudio.Shell.11.0` aktuální verzí knihovny MPF dll.)

 Chcete-li zobrazit dialogové okno, zavolejte "**ShowModal ()** " na třídu přes **ShowDialog ()** . **ShowModal ()** nastaví správný modální stav v prostředí, zajistí, že se dialog v nadřazeném okně zařadí do středu, a tak dále.

 Kód je následujícím způsobem:

```
MyWindow window = new MyWindow();
window.ShowModal()

```

 **ShowModal** vrací BOOL? (Nullable Boolean) se **DialogResult**, který může být v případě potřeby použit. Návratová hodnota má hodnotu true, pokud bylo dialogové okno zavřeno s **OK**.

 Pokud potřebujete zobrazit některé uživatelské rozhraní WPF, které není dialog a je hostováno ve vlastním **HwndSource**, například v místním okně nebo v podřízeném okně WPF okna nadřazeného okna systému Windows, bude nutné nastavit **FontFamily** a **FontSize** v kořenovém elementu prvku WPF. (Prostředí v hlavním okně nastaví vlastnosti, ale nebude možné zdědit minulé HWND). Prostředí obsahuje prostředky, ke kterým může být vázána vlastnosti, následujícím způsobem:

```
<Setter property="FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" />
<Setter property="FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" />

```

### <a name="BKMK_Formatting"></a>Formátování (škálování/tučné) – referenční informace
 Některá dialogová okna, aby konkrétní text, který má být tučného písma nebo velikost než písmo prostředí. Dříve byly písma větší než písmo prostředí kódovaný jako "písmo prostředí + 2" nebo podobné. Používání fragmentů kódu zadaná podporu vysokých hodnot DPI monitorování a ujistěte se, že zobrazovaný text vždy se zobrazí v správnou velikost a váhy (jako jsou Light nebo Semilight).

> **Poznámka: před použitím formátování se ujistěte, že budete postupovat podle pokynů, které najdete ve [stylu textu](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).**

 Škálování prostředí písma, nastavte styl TextBlock nebo popisku, jak je uvedeno. Každá z těchto fragmentů kódu používá správně, bude generovat použitím správného písma, včetně změn odpovídající velikost a váhy záznamu.

 Je-li "vsui nebyla rozpoznána" odkaz na obor názvů Microsoft.VisualStudio.Shell:

```
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"

```

#### <a name="375-environment-font--light"></a>Písmo prostředí 375 % + světla
 **Zobrazuje se jako:** 34 PT Segoe UI Light.

 **Použijte pro:** (vzácné) jedinečné BRANDINGOVÉ uživatelské rozhraní, jako je například na úvodní stránce.

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey}}">TextBlock: 375 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey}}">Label: 375 Percent Scaling</Label>

```

#### <a name="310-environment-font--light"></a>Písmo prostředí 310 % + světla
 **Zobrazuje se jako:** 28 bodů Segoe UI Light.

 **Použijte pro:** názvy dialogových oken velkých podpisů, hlavní nadpis v sestavách

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey}}">TextBlock: 310 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey}}">Label: 310 Percent Scaling</Label>

```

#### <a name="200-environment-font--semilight"></a>Písmo prostředí 200 % + Semilight
 **Vypadá takto:** 18 bodů Segoe UI Semilight

 **Použít pro:** dílčí záhlaví, názvy v malých a středně velkých dialogových oknech

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey}}">TextBlock: 200 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey}}">Label: 200 Percent Scaling</Label>

```

#### <a name="155-environment-font"></a>155 % prostředí písma
 **Zobrazuje se jako:** 14 bodů Segoe UI

 **Použít pro:** nadpisy oddílů v uživatelském rozhraní nebo sestavách dokumentu

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey}}">TextBlock: 155 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey}}">Label: 155 Percent Scaling</Label>

```

#### <a name="133-environment-font"></a>133 % prostředí písma
 **Vypadá takto:** Segoe UI 12 bodů

 **Použít pro:** menší podpozice v dialogových oknech podpisů a v uživatelském rozhraní dokumentu

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey}}">TextBlock: 133 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey}}">Label: 133 Percent Scaling</Label>

```

#### <a name="122-environment-font"></a>Písmo prostředí 122 %
 **Zobrazuje se jako:** 11 bodů Segoe UI

 **Používá se pro:** nadpisy oddílů v dialogových oknech podpisů, hlavních uzlech ve stromovém zobrazení, svislé navigaci karet.

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey}}">TextBlock: 122 Percent Scaling</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey}}">Label: 122 Percent Scaling</Label>

```

#### <a name="environment-font--bold"></a>Písmo prostředí + tučného písma
 **Zobrazuje se jako:** tučné 9 pt Segoe UI

 **Použijte pro:** Labels a podhlaves v dialogových oknech podpisů, sestavách a ve správném uživatelském rozhraní dokumentu.

 **Procedurální kód:** Kde "textBlock" je dříve definovaný TextBlock a "label" je dříve definovaný popisek.

```
textBlock.SetResourceReference(TextBlock.StyleProperty,  
        VsResourceKeys.TextBlockEnvironmentBoldStyleKey); 
label.SetResourceReference(Label.StyleProperty,  
        VsResourceKeys.LabelEnvironmentBoldStyleKey);

```

 **XAML:** Nastavte styl TextBlock nebo popisku, jak je znázorněno na obrázku.

```
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironmentBoldStyleKey}}"> Bold TextBlock</TextBlock> 
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironmentBoldStyleKey}}"> Bold Label</Label>

```

### <a name="localizable-styles"></a>Lokalizovatelné styly
 V některých případech Lokalizátoři muset upravit styly písem definované pro různá národní prostředí, jako je například tučné odebrání text pro východoasijské jazyky. Chcete-li lokalizace styly písem je to možné, musí být tyto styly v souboru .resx. Nejlepší způsob, jak to provést a přesto upravit styly písem definované v nástroji Návrhář formulářů sady Visual Studio je explicitně nastavit styly písem v době návrhu. I když to vytvoří objekt celé písmo a zdát, že k rozdělení dědění nadřazeného písma, pouze vlastnost FontStyle slouží k nastavení písma.

 Řešením je zapojit událost **FontChanged** formuláře dialogového okna. V události **FontChanged** Projděte všechny ovládací prvky a ověřte, zda je jejich písmo nastaveno. Pokud je nastavena, změňte ho na nové písmo na základě formuláře písma a předchozí styl písma ovládacího prvku. Příklad v kódu je:

```
private void Form1_FontChanged(object sender, System.EventArgs e)
{
          SetFontStyles();
}

/// <summary>
/// SetFontStyles - This function will iterate all controls on a page
/// and recreate their font with the desired fontstyle.
/// It should be called in the OnFontChanged handler (and also in the constructor
/// in case the IUIService is not available so OnFontChange doesn't fire).
/// This way, when the VS shell font is given to us the controls that have
/// a different style for the font (bolded for example) will recreate their font
/// and use the VS shell font but with a style variation (bolded ...).
/// </summary>
protected void SetFontStyles()
{
     SetFontStyles(this, this, this.Font);
}

protected static void SetFontStyles(Control topControl, Control parent, Font referenceFont)
{
     foreach(Control c in parent.Controls)
     {
          if (c.Controls != null && c.Controls.Count > 0) {
               SetFontStyles(topControl, c, referenceFont);
          }
          if (c.Font != topControl.Font) {
               c.Font = new Font(referenceFont, c.Font.Style);
          }
     }
}
```

 Tento kód použít zaručuje, že dojde k aktualizaci formuláře písma, bude písma ovládací prvky také aktualizovat. Tato metoda by měla být volána také z konstruktoru formuláře, protože dialogové okno může selhat při získání instance **IUIService** a událost **FontChanged** nikdy neproběhne. Zavěšení **FontChanged** umožní dialogům dynamicky vybrat nové písmo, i když už je dialog otevřený.

### <a name="testing-the-environment-font"></a>Testování písmo prostředí
 Aby bylo zajištěno, že vaše uživatelské rozhraní používá písmo prostředí a respektuje nastavení velikosti, otevřete **nástroje > možnosti > prostředí > písma a barvy** a v rozevírací nabídce "Zobrazit nastavení pro:" vyberte možnost "písmo prostředí".

 ![Stránka písma a barvy v dialogovém &#62; okně Možnosti nástrojů](../../extensibility/ux-guidelines/media/0201-a-optionsfonts.png "0201 – a_OptionsFonts")

 **Nastavení písem a barev v dialogovém okně nástroje > Možnosti**

 Nastavte písmo na velmi jiné než výchozí. Aby bylo zřejmé který uživatelského rozhraní se neaktualizuje, zvolte písma s patek (například "Times nové Roman") a nastavte velmi velké velikosti. Otestujte uživatelské rozhraní k zajištění, že respektuje prostředí. Tady je příklad použití dialogového okna licence:

 ![Příklad dialogového okna bez použití písma prostředí](../../extensibility/ux-guidelines/media/0201-b-wrongfontdialog.png "0201 – b_WrongFontDialog")

 **Příklad textu uživatelského rozhraní, které nerespektuje písmo prostředí**

 "Informace o uživateli" a "Informace o produktu" nejsou v tomto případě respektování písma. V některých případech to může být na volbu explicitní návrhu, ale může jít o chybu, pokud není zadán explicitní písma v rámci specifikace redline.

 Pokud chcete písmo obnovit, klikněte na "použít výchozí" v části **nástroje > možnosti > prostředí > písma a barvy**.

## <a name="BKMK_TextStyle"></a>Styl textu
 Styl textu odkazuje na velikost písma, váha a malých a velkých písmen. Pokyny k implementaci najdete v tématu [Písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).

### <a name="text-casing"></a>Text malých a velkých písmen

#### <a name="all-caps"></a>Všechna písmena velká
 Nepoužívejte všechna písmena velká pro nadpisy a popisky v sadě Visual Studio.

#### <a name="all-lowercase"></a>Všechna písmena malá
 Nepoužívejte jenom malá písmena pro názvy a popisky v sadě Visual Studio.

#### <a name="sentence-and-title-case"></a>Věty a název případu
 Text v sadě Visual Studio by měl použít první velká písmena nebo velké pouze první písmeno, v závislosti na situaci.

|Název případem použití:|Používejte velká písmena pro:|
|-------------------------|----------------------------|
|Dialogové okno názvy|Popisky|
|Skupinové rámečky|Zaškrtávací políčka|
|Položky nabídky|Přepínací tlačítka|
|Položek kontextové nabídky|Seznam položek pole|
|Tlačítka|Stavové řádky|
|Tabulka popisky||
|Záhlaví sloupců||
|Popisy tlačítek||

##### <a name="title-case"></a>Všechna první písmena velká
 Mena všech slov velká je styl, ve kterém jsou první písmena většinu nebo všechny slov v rámci frázi velkými písmeny. V sadě Visual Studio se používá mena všech slov velká pro mnoho položek, včetně:

- **Popisy.** Příklad: "náhled vybrané položky"

- **Záhlaví sloupců** Příklad: "systém odpovědi"

- **Položky nabídky** Příklad: "Uložit vše"

  Při použití mena všech slov velká, toto jsou pokyny pro kdy velké první písmeno slova a kdy je nechat, malá písmena:

|Velká písmena|Komentáře a příklady|
|---------------|---------------------------|
|Všechny podstatná jména||
|Všechny akce|Včetně "Je" a další formy "chcete být"|
|Všechny příslovcí|Včetně "Než" a "Data"|
|Všechny přídavných jmen|Včetně "This" a ""|
|Všechny zájmena|Včetně přivlastňovacího pádu "Své" i "Je," snížení zastupovat "," a příkaz "je"|
|První a poslední slov bez ohledu na to částí řeči||
|Předložky, které jsou součástí příkaz fráze|"Zavření si všechny Windows" nebo "Vypínání systému"|
|Všechna písmena zkratka|HTML, XML, ADRESA URL, ROZHRANÍ IDE, RGB|
|Druhá slovo v složené slovo, pokud je to podstatné jméno nebo přídavného správných jména, nebo máte stejnou váhu slova|Přístup pro čtení a zápis křížových odkazů, předběžného softwaru, Run-Time|

|Malá písmena|Příklady|
|---------------|--------------|
|Druhý slovo v složené slovo, je-li další slovní nebo jiném úpravy první slovo čase či osobě|Postupy:, zkuste vypnout|
|Články, pokud jeden není první slovo v názvu|,|
|Souřadnice spojky|a, ale pro, ani, nebo|
|Předložky obsahující slova čtyři nebo méně písmena mimo příkaz fráze|do do, jako u předem, v horní části|
|"Do" při použití v nekonečná fráze|"Jak formátování pevného disku"|

##### <a name="sentence-case"></a>Velké pouze první písmeno
 Věty je metoda standardní malá a velká písmena pro zápis, ve kterém je velké pouze první slovo věty, spolu s jakékoli podstatná jména správné a zastupovat "I." Obecně je snadnější po celém světě cílové skupiny, číst, zejména když obsah bude fungovat na počítači věty. Používejte velká písmena pro:

1. **Zprávy stavového řádku.** Tyto jsou jednoduché a krátké a poskytují jenom informace o stavu. Příklad: "načítání souboru projektu"

2. **Všechny ostatní prvky uživatelského rozhraní**, včetně popisků, zaškrtávacích políček, přepínačů a položek seznamu Příklad: "všechny položky v seznamu vyberte"

### <a name="text-formatting"></a>Formátování textu
 Výchozí formátování textu v Visual Studio 2013 je řízeno pomocí [písma prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont). Tato služba pomáhá zajistit vzhled písma konzistentní v celém rozhraní IDE (integrované vývojové prostředí) a je nutné je použít k zajištění konzistentního prostředí pro vaše uživatele.

 Výchozí velikost písma služba Visual Studio využívá pochází z Windows a zobrazí se jako 9 pt.

 Můžete použít formátování písma prostředí. Toto téma popisuje, jak a kde použít styly. Informace o implementaci najdete v tématu [Písmo prostředí](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).

#### <a name="bold-text"></a>Tučný text
 Tučný text je používat střídmě, v sadě Visual Studio a by měl být vyhrazen pro:

- dotaz popisky v průvodcích

- určení aktivního projektu v Průzkumníku řešení

- přepsat hodnoty v okně nástroje Vlastnosti

- určitých událostí v rozevíracích seznamech editoru jazyka Visual Basic

- obsah generovaný serverem osnovy dokumentu pro webové stránky

- oddíl hlavičky v komplexní dialogové okno nebo návrhář uživatelského rozhraní

#### <a name="italics"></a>Kurzíva
 Visual Studio nepoužívá kurzívy nebo tučně formátovaný text kurzívou.

#### <a name="color"></a>Barva

- Modrá je vyhrazená pro hypertextové odkazy (navigaci a příkazů) a byste nikdy neměli používat pro orientaci.

- Větší záhlaví (písmo prostředí x 155 % nebo vyšší) můžou mít barvy pro tyto účely:

  - K poskytování vizuální vzhled podpis uživatelského rozhraní Visual Studio

  - Chcete-li upoutat pozornost na konkrétní oblasti

  - Nabízí osvobození od standardního prostředí tmavě šedé/Černá barva textu

- Barva záhlaví by je měli využít stávající sady Visual Studio značkové barvy, především hlavní nachová #FF68217A.

- Při použití barev v nadpisech musíte dodržovat [pokyny k barvě Windows](https://msdn.microsoft.com/library/dn742482.aspx), včetně poměru kontrastu a dalších otázek dostupnosti.

### <a name="font-size"></a>Velikost písma
 Visual Studio UI návrh funkce světlejší vzhled více prázdnými znaky. Tam, kde je to možné, byly pruhy chrome a názvu nižší nebo odebrán. Požadavek v sadě Visual Studio při informace hustota Typografie i nadále být důležité, s důrazem na otevřenější řádkování a změna velikosti písma a váhy.

 V tabulce dole najdete obsahuje podrobnosti o návrhu a vizuální příklady pro zobrazení písma použitého v sadě Visual Studio. Několik variant písma zobrazení mít velikost i váha, jako je například Semilight nebo světle, zakódovaný do jejich výskytu.

 Fragmenty kódu implementace pro všechna zobrazovaná písma se dají najít v [odkazu formátování (škálování/tučné)](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_Formatting).

#### <a name="375-environment-font--light"></a>Písmo prostředí 375 % + světla

|||
|-|-|
|**Použití:** Časté. Jedinečné obchodní značku pouze uživatelské rozhraní.<br /><br /> **Postup**<br /><br /> -Používejte velká písmena<br />-Vždy používejte lehký<br /><br /> **Ne:**<br /><br /> – Použijte pro uživatelské rozhraní než podpis uživatelského rozhraní, jako je například úvodní stránka<br />-Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />– Použijte v oknech nástrojů|**Zobrazuje se jako:** 34 PT Segoe UI Light.<br /><br /> **Příklad vizuálu:**<br /><br /> *Aktuálně se nepoužívá. Lze použít na úvodní stránce.*|

#### <a name="310-environment-font--light"></a>Písmo prostředí 310 % + světla

|||
|-|-|
|**Využívání**<br /><br /> -Větší záhlaví v dialogových oknech podpis<br />– Nadpis hlavní sestava<br /><br /> **Postup**<br /><br /> -Používejte velká písmena<br />-Vždy používejte lehký<br /><br /> **Ne:**<br /><br /> – Použijte pro uživatelské rozhraní než podpis uživatelského rozhraní, jako je například úvodní stránka<br />-Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />– Použijte v oknech nástrojů|**Zobrazuje se jako:** 28 bodů Segoe UI Light.<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad 310% – nadpis světla &#43; písma prostředí](../../extensibility/ux-guidelines/media/0202-a-ef310.png "0202 – a_EF310")|

#### <a name="200-environment-font--semilight"></a>Písmo prostředí 200 % + Semilight

|||
|-|-|
|**Využívání**<br /><br /> -Položek<br />– Názvy v dialogových oknech malé a střední<br /><br /> **Postup**<br /><br /> -Používejte velká písmena<br />-Vždy používejte Semilight váhy<br /><br /> **Ne:**<br /><br /> -Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />– Použijte v oknech nástrojů|**Vypadá takto:** 18 bodů Segoe UI Semillight<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad 200% fontu &#43; prostředí Semilight](../../extensibility/ux-guidelines/media/0202-b-ef200.png "0202 – b_EF200")|

#### <a name="155-environment-font"></a>155 % prostředí písma

|||
|-|-|
|**Využívání**<br /><br /> -Section záhlaví v dokumentu a uživatelského rozhraní<br />-Sestavy<br /><br /> **Do:** Použít případ věty<br /><br /> **Ne:**<br /><br /> -Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />– Použijte v oknech nástrojů|**Zobrazuje se jako:** 14 bodů Segoe UI<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad 155% nadpisu písma prostředí](../../extensibility/ux-guidelines/media/0202-c-ef155.png "0202 – c_EF155")|

#### <a name="133-environment-font"></a>133 % prostředí písma

|||
|-|-|
|**Využívání**<br /><br /> -Menší položek v dialogových oknech podpis<br />-Menší položky v dokumentu a uživatelského rozhraní<br /><br /> **Do:** Použít případ věty<br /><br /> **Ne:**<br /><br /> -Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />– Použijte v oknech nástrojů|**Vypadá takto:** Segoe UI 12 bodů<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad 133% nadpisu písma prostředí](../../extensibility/ux-guidelines/media/0202-d-ef133.png "0202 – d_EF133")|

#### <a name="122-environment-font"></a>Písmo prostředí 122 %

|||
|-|-|
|**Využívání**<br /><br /> -Section záhlaví v dialogových oknech podpis<br />-Hlavní uzly ve stromovém zobrazení<br />– Navigace vertikální tabulátor<br /><br /> **Do:** Použít případ věty<br /><br /> **Ne:**<br /><br /> -Tučného písma, kurzívy nebo tučné, kurzíva<br />-Použití textu<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />– Použijte v oknech nástrojů|**Zobrazuje se jako:** 11 bodů Segoe UI<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad 122% nadpisu písma prostředí](../../extensibility/ux-guidelines/media/0202-e-ef122.png "0202 – e_EF122")|

#### <a name="environment-font--bold"></a>Písmo prostředí + tučného písma

|||
|-|-|
|**Využívání**<br /><br /> -Popisků a podnadpisy v dialogových oknech podpis<br />-Popisků a podnadpisy v sestavách<br />-Popisků a podnadpisy v dokumentu uživatelského rozhraní<br /><br /> **Postup**<br /><br /> -Používejte velká písmena<br />– Použití tučného písma váhy<br /><br /> **Ne:**<br /><br /> -Kurzívy nebo tučné, kurzíva<br />-Použití textu<br />-Použít ve standardní ovládací prvky sady Visual Studio<br />– Použijte v oknech nástrojů|**Zobrazuje se jako:** tučné 9 pt Segoe UI<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad písma &#43; prostředí nadpisu tučně](../../extensibility/ux-guidelines/media/0202-f-efb.png "0202 – f_EFB")|

#### <a name="environment-font"></a>Písmo prostředí

|||
|-|-|
|**Použití:** Všechen jiný text<br /><br /> **Do:** Použít případ věty<br /><br /> **Nepoužívejte:** Kurzíva nebo Tučná kurzíva|**Zobrazuje se jako:** 9 bodů Segoe UI<br /><br /> **Příklad vizuálu:**<br /><br /> ![Příklad písma prostředí](../../extensibility/ux-guidelines/media/0202-g-ef.png "0202 – g_EF")|

### <a name="padding-and-spacing"></a>Odsazení a mezery
 Záhlaví vyžadují prostor kolem nich jim poskytnout příslušné zvýraznění. Tento prostor se liší v závislosti na velikosti bodu a co dalšího je v záhlaví, jako je například vodorovná čára nebo řádek textu v prostředí písma.

- Ideální odsazení pro nadpis sám o sobě by měl být 90 % prostoru výška velké znak. Například záhlaví Segoe UI Light 28 pt má limit výšku 26 pt a odsazení by měla být přibližně 23 pt nebo přibližně 31 pixelů.

- Minimální místo kolem nadpis by měl být 50 % výšky velké znak. Při nadpis doplněny pravidlo nebo jiný prvek těsným lze méně místa.

- Tučný text písmo prostředí by mělo vycházet výchozí výška řádkování a odsazení.

## <a name="see-also"></a>Viz také
 [MSDN: písma (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742483\(v=vs.85\).aspx) [MSDN: text uživatelského rozhraní (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742478\(v=vs.85\).aspx)
