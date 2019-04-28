---
title: 'Postupy: Vytváření řešení jazyka specifického pro doménu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.designerwizard
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools], creating domain-specific language
- Domain-Specific Language Tools, creating solutions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ac8a47aeca8875dabe3fdf388e9a73d68ec514e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445202"
---
# <a name="how-to-create-a-domain-specific-language-solution"></a>Postupy: Vytváření řešení jazyka specifického pro doménu
Jazyka specifického pro doménu (DSL) se vytvoří s použitím specializovaná řešení sady Visual Studio.

## <a name="prerequisites"></a>Požadavky

Před zahájením tohoto postupu, tyto součásti nainstalujte:

- Visual Studio
- Visual Studio SDK (instalují jako součást **vývoj rozšíření sady Visual Studio** úlohy)
- Sada Modeling SDK (nainstalován jako součást sady Visual Studio)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="creating-a-domain-specific-language-solution"></a>Vytváření řešení jazyka specifického pro doménu

1. Spusťte DSL Průvodce vytvořením nového **návrháře jazyka specifického pro doménu** projektu.

   > [!NOTE]
   > Pokud možno název, který jste vybrali pro projekt by měl být platný Vizuálu C# identifikátor protože může být použit pro generování kódu.

   ::: moniker range="vs-2017"

   ![Vytvoření dialogového okna DSL](../modeling/media/create_dsldialog.png)

   ::: moniker-end

2. Zvolte šablonu DSL.

    Na **vybrat možnosti jazyka specifického pro doménu** stránky, vyberte jednu z šablon řešení, jako **minimální jazykový**. Zvolte šablonu, která se podobá DSL, který chcete vytvořit.

    Další informace o šablonách řešení, najdete v části [výběr šablony řešení jazyka specifického pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).

3. Zadejte příponu názvu souboru na **přípona souboru** stránky. By měl být jedinečný ve vašem počítači a ve všech počítačích, na kterém chcete nainstalovat DSL. Zobrazí se zpráva **žádné aplikace ani editory sady Visual Studio toto rozšíření využít**.

   - Pokud přípona názvu souboru jste použili v předchozí experimentální DSL, která plně nenainstalovali, můžete vymazat jejich odhlašování pomocí **resetovat experimentální instanci** nástroj, který se nachází v nabídce sady Visual Studio SDK.

   - Pokud jiné rozšíření sady Visual Studio, který používá tuto příponu souboru byl plně nainstalován v počítači, vezměte v úvahu odinstalujete ji. Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.

4. Zkontrolujte a v případě potřeby upravit, pole na zbývajících stránkách průvodce. Pokud jste s nastavením spokojeni, klikněte na tlačítko **Dokončit**. Další informace o nastaveních, která najdete v tématu [stránky průvodce Návrhář DSL](#settings).

    Průvodce vytvoří řešení, která má dva projekty, které jsou pojmenovány **Dsl** a **DslPackage**.

   > [!NOTE]
   > Pokud se zobrazí zpráva, která vás upozorní, není ke spuštění textové šablony z nedůvěryhodných zdrojů, klikněte na tlačítko **OK**. Můžete nastavit tato zpráva se zobrazí znovu.

## <a name="settings"></a> Na stránkách průvodce návrhářem DSL
 Můžete nechat několik polí nezmění z výchozí hodnoty. Nicméně Ujistěte se, že pole přípona souboru je nastavit.

### <a name="solution-settings-page"></a>Stránka nastavení řešení
 **Kterou šablonu chcete vaše jazyka specifického pro doménu vycházet?**
Zvolte šablonu, která se podobá DSL, který chcete vytvořit. Různé šablony poskytují pohodlný počátečních bodů. Když vyberete šablonu řešení, Průvodce zobrazí popis. Další informace o šablonách řešení, najdete v části [výběr šablony řešení jazyka specifického pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).

 **Co chcete jazyka specifického pro doménu pojmenovat?**
Výchozí hodnota je název řešení. Kód je generován z této hodnoty. Musí být platný jako název třídy C#.

### <a name="file-extension-page"></a>Stránka přípona souboru
 **Jaká rozšíření by měly soubory modelu použití?**
Zadejte novou příponu souboru.

 Ověřte, že tato přípona souboru nebyla již byl registrován pro použití v tomto počítači následujícím způsobem:

 Podívejte se do části **další nástroje a aplikace zaregistrované ke zpracování této přípony**. Pokud se zobrazí zpráva **žádné aplikace ani editory sady Visual Studio toto rozšíření využít**, můžete použít tuto příponu souboru.

 Pokud se zobrazí seznam nástrojů nebo balíčky, proveďte jednu z následujících akcí:

- Zadejte jinou příponu souboru.

     \- nebo –

- Resetujte experimentální instanci sady Visual Studio. Zruší registraci všech DSL, které jste dříve vytvořili. Na **Start** nabídky, klikněte na tlačítko **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a potom **resetovat Microsoft Visual Studio 2010 experimentální instanci**. Můžete znovu sestavit jiných DSL, který chcete znovu použít.

     \- nebo –

- Pokud rozšíření aplikace Visual Studio, který používá tuto příponu souboru byl plně nainstalován v počítači, odinstalujte ji. Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.

### <a name="product-settings-page"></a>Stránka nastavení produktu
 **Jaký je název produktu, který nový jazyk specifický pro doménu patří?**
Výchozí hodnota je název DSL.

 Tato hodnota se používá v Průzkumníku Windows (nebo Průzkumníka souborů) k popisu souborů, které mají tuto příponu souboru.

 **Jaký je název společnosti, která tento produkt patří?**
Název vaší společnosti.

 Tato hodnota je součástí souboru AssemblyInfo vlastnosti balíčku DSL.

 **Co je kořenový obor názvů pro projekty v tomto řešení?**
Výchozí hodnota pro název skládající se z vaší společnosti a názvy produktů.

### <a name="signing-page"></a>stránka Podepisování
 **Vytvořit soubor klíče se silným názvem** výchozí možností je vytvořit nový klíč k podepsání sestavení DSL.

 **Použít existující klíč se silným názvem** tuto možnost použijte, pokud chcete integrovat vašeho DSL pomocí jiného sestavení.

 Další informace o silné názvy najdete v tématu [vytvoření a použití sestavení](http://go.microsoft.com/fwlink/?LinkId=186073).

## <a name="see-also"></a>Viz také:

- [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
