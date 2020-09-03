---
title: 'Postupy: vytvoření řešení jazyka specifického pro doménu | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.dsltools.designerwizard
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools], creating domain-specific language
- Domain-Specific Language Tools, creating solutions
ms.assetid: e585b63b-34d2-405a-8d81-39ea22317975
caps.latest.revision: 43
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 227838334067d33c8a50c81d3a3c013c6baee356
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85533078"
---
# <a name="how-to-create-a-domain-specific-language-solution"></a>Postupy: Vytváření řešení jazyka specifického pro doménu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jazyk specifický pro doménu (DSL) se vytvoří pomocí specializovaného [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení.

## <a name="prerequisites"></a>Předpoklady
 Než budete moct tento postup spustit, musíte nejdřív nainstalovat tyto komponenty:

|Produkt|Odkaz ke stažení|
|-|-|
|[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]|[https://www.visualstudio.com/](https://www.visualstudio.com/)|
|[!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)]|[Visual Studio SDK](../extensibility/visual-studio-sdk.md)|
|Sada SDK pro vizualizaci a modelování sady Visual Studio|[Stažení sady SDK pro modelování](https://www.microsoft.com/download/details.aspx?id=48148)|

## <a name="creating-a-domain-specific-language-solution"></a>Vytváření řešení jazyka specifického pro doménu

#### <a name="to-create-a-domain-specific-language-solution"></a>Vytvoření řešení jazyka specifického pro doménu

1. Spusťte Průvodce DSL.

   1. V nabídce **soubor** přejděte na příkaz **Nový**a klikněte na **projekt**.

   2. Zobrazí se dialogové okno **Nový projekt**.

   3. V části **typy projektů**rozbalte uzel **ostatní typy projektů** a klikněte na **rozšiřitelnost**.

   4. Klikněte na **Návrhář jazyka specifického pro doménu**.

   5. Do pole **název** zadejte název řešení. Klikněte na **OK**.

       Zobrazí se **Průvodce návrháře jazyka specifického pro doménu** .

      > [!NOTE]
      > Název, který zadáte, by měl být platným identifikátorem jazyka Visual C#, protože může být použit pro generování kódu.

      ![Dialog vytvořit DSL](../modeling/media/create-dsldialog.png "Create_DSLDialog")

2. Vyberte šablonu DSL.

    Na stránce **Výběr možností jazyka specifického pro doménu** vyberte jednu z šablon řešení, jako je například **Minimální jazyk**. Vyberte šablonu, která je podobná DSL, kterou chcete vytvořit.

    Další informace o šablonách řešení najdete v tématu [Výběr šablony řešení jazyka specifického pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).

3. Na stránce **Přípona souboru** zadejte příponu filename. Měl by být jedinečný v počítači a na všech počítačích, na které chcete nainstalovat DSL. Měla by se zobrazit zpráva **žádné aplikace ani editory sady Visual Studio nepoužívají toto rozšíření**.

   - Pokud jste v předchozích experimentálních DSL použili příponu názvu souboru, která nebyla plně nainstalovaná, můžete je vymazat pomocí nástroje pro **obnovení experimentální instance** , který lze najít v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nabídce SDK.

   - Pokud [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] je v počítači plně nainstalovaná jiná přípona této přípony souboru, zvažte její odinstalaci. V nabídce **nástroje** klikněte na **Správce rozšíření**.

4. Zkontrolujte a v případě potřeby upravte pole na zbývajících stránkách průvodce. Až budete s nastavením spokojeni, klikněte na **Dokončit**. Další informace o nastaveních najdete na [stránce průvodce návrháře DSL](#settings).

    Průvodce vytvoří řešení, které má dva projekty s názvem **DSL** a **DslPackage**.

   > [!NOTE]
   > Pokud se zobrazí zpráva upozorňující, že nespouštíte textové šablony z nedůvěryhodných zdrojů, klikněte na tlačítko **OK**. Tuto zprávu můžete nastavit tak, aby se nezobrazovala znovu.

## <a name="the-dsl-designer-wizard-pages"></a><a name="settings"></a> Stránky průvodce návrháře DSL
 Z jejich výchozích hodnot můžete nechat některá z těchto polí beze změny. Ujistěte se však, že jste nastavili pole Přípona souboru.

### <a name="solution-settings-page"></a>Stránka nastavení řešení
 **Jakou šablonu chcete pro konkrétní jazyk domény založit?**
Vyberte šablonu, která je podobná DSL, kterou chcete vytvořit. Různé šablony poskytují pohodlný počáteční bod. Když vyberete šablonu řešení, Průvodce zobrazí popis. Další informace o šablonách řešení najdete v tématu [Výběr šablony řešení jazyka specifického pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).

 **Jak chcete pojmenovat jazyk specifický pro doménu?**
Ve výchozím nastavení se jedná o název řešení. Z této hodnoty je vygenerován kód. Musí být platný jako název třídy jazyka C#.

### <a name="file-extension-page"></a>Stránka s příponou souboru
 **Jakou příponu mají soubory modelu používat?**
Zadejte novou příponu souboru.

 Ověřte, že tato přípona souboru ještě není zaregistrovaná pro použití v tomto počítači, a to následujícím způsobem:

 Podívejte **se na jiné nástroje a aplikace zaregistrované pro zpracování tohoto rozšíření**. Pokud se zobrazí zpráva **žádné aplikace nebo editory sady Visual Studio nepoužívají toto rozšíření**, můžete použít tuto příponu souboru.

 Pokud se zobrazí seznam nástrojů nebo balíčků, měli byste provést jednu z následujících akcí:

- Zadejte jinou příponu souboru.

     \- ani

- Resetovat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] experimentální instanci. Tím zrušíte registraci všech dříve vytvořených DSL. V nabídce **Start** klikněte na **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a pak **na experimentální instanci Microsoft Visual Studio 2010 obnovte**. Můžete znovu sestavit jakýkoli jiný DSL, který chcete znovu použít.

     \- ani

- Pokud je [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření, které tuto příponu souboru používá, v počítači plně nainstalované, odinstalujte ho. V nabídce **nástroje** klikněte na **Správce rozšíření**.

### <a name="product-settings-page"></a>Stránka nastavení produktu
 **Jaký je název produktu, ke kterému patří nový jazyk specifický pro doménu?**
Použije se výchozí název DSL.

 Tato hodnota se používá v Průzkumníkovi Windows (nebo v Průzkumníku souborů) k popisu souborů, které mají tuto příponu souboru.

 **Jaký je název společnosti, do které produkt patří?**
Název vaší společnosti.

 Tato hodnota se začlení do vlastností AssemblyInfo vašeho balíčku DSL.

 **Jaký je kořenový obor názvů pro projekty v tomto řešení?**
Tento název se použije jako název složený z názvu vaší společnosti a produktu.

### <a name="signing-page"></a>stránka Podepisování
 **Vytvořit soubor klíče se silným názvem** Výchozí možnost je vytvořit nový klíč pro podepsání vašeho sestavení DSL.

 **Použít existující klíč se silným názvem** Tuto možnost použijte, pokud chcete své DSL integrovat s jiným sestavením.

 Další informace o silných názvech naleznete v tématu [vytváření a používání sestavení se silným názvem](/dotnet/standard/assembly/create-use-strong-named).

## <a name="see-also"></a>Viz také
 [Definování jazyka](../modeling/how-to-define-a-domain-specific-language.md) [nástroje DSL slovníku](/previous-versions/bb126564(v=vs.100)) specifického pro doménu
