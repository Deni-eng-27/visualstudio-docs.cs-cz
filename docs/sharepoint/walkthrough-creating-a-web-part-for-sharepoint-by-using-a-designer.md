---
title: 'Průvodce: Vytvoření webové části pro službu SharePoint pomocí návrháře | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], designer
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fa5817bb7c20cf58457281667dda76ac43608647
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875332"
---
# <a name="walkthrough-create-a-web-part-for-sharepoint-by-using-a-designer"></a>Průvodce: Vytvoření webové části pro službu SharePoint pomocí návrháře

Pokud vytváříte webové částí webu služby SharePoint, uživatelé mohou přímo upravit obsah, vzhled a chování stránky na tomto webu pomocí prohlížeče. Tento návod ukazuje, jak vizuálně vytvářet webové části služby SharePoint pomocí **vizuální webové části** šablony projektu v sadě Visual Studio.

Webová část, kterou vytvoříte zobrazí zobrazení měsíčního kalendáře a zaškrtávací políčko pro každý seznam kalendáře na webu. Uživatelé mohou zadat, kalendář, který seznamů pro zahrnutí do zobrazení měsíčního kalendáře zaškrtnutím políčka.

Tento návod znázorňuje následující úlohy:

- Vytvoření webové části pomocí **vizuální webové části** šablony projektu.
- Návrh webové části pomocí návrháře Visual Web Developer v sadě Visual Studio.
- Přidávání kódu pro zpracování událostí ovládacích prvků ve webové části.
- Testování webové části služby SharePoint.

    > [!NOTE]
    > Váš počítač může v následujících pokynech zobrazovat jiné názvy nebo umístění některých prvků uživatelského rozhraní pro sadu Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Zobrazit [přizpůsobit prostředí IDE sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto návodu budete potřebovat následující komponenty:

- Podporované edice systému Windows a SharePoint.

## <a name="create-a-web-part-project"></a>Vytvoření projektu webové části

Nejprve vytvořte projekt webové části pomocí **vizuální webové části** šablony projektu.

1. Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí **spustit jako správce** možnost.

2. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

     Zobrazí se dialogové okno **Nový projekt**.

3. V **nový projekt** dialogové okno, v části **Visual C#** nebo **jazyka Visual Basic**, rozbalte **Office/SharePoint**a klikněte na tlačítko  **Řešení služby SharePoint** kategorie.

4. V seznamu šablon vyberte **SharePoint 2013 - Visual Web Part** šablony a klikněte na tlačítko **OK** tlačítko.

     **Průvodce přizpůsobením SharePoint** se zobrazí. Pomocí tohoto průvodce můžete určit web, který budete používat k ladění projektu a úroveň důvěryhodnosti řešení.

5. V **co je úroveň důvěryhodnosti pro toto řešení SharePoint?** zvolte **nasadit jako řešení farmy** přepínač.

6. Zvolte **Dokončit** tlačítko k přijetí výchozího místního webu služby SharePoint.

## <a name="designing-the-web-part"></a>Návrh webové části

Návrh webové části přidáním ovládacích prvků **nástrojů** na plochu návrháře Visual Web Developer.

1. V aplikaci Visual Web Developer, zvolte **návrhu** tab přepnete na zobrazení návrhu.

2. V panelu nabídky zvolte **zobrazení** > **nástrojů**.

3. V **standardní** uzlu **nástrojů**, zvolte **CheckBoxList** ovládací prvek a potom proveďte jednu z následujících kroků:

    - Otevřete místní nabídku **CheckBoxList** ovládací prvek, zvolte **kopírování**, otevřete místní nabídku pro první řádek v návrháři a klikněte na tlačítko **vložit**.

    - Přetáhněte **CheckBoxList** ovládacího prvku **nástrojů**a připojte ho k první řádek v návrháři.

4. Opakujte předchozí krok, ale přesuňte tlačítko na další řádek v návrháři.

5. V návrháři, zvolte **Button1** tlačítko.

6. V panelu nabídky zvolte **zobrazení** > **okno vlastností**.

     **Vlastnosti** otevře se okno.

7. V **Text** vlastnosti tlačítka, zadejte **aktualizace**.

## <a name="handling-the-events-of-controls-on-the-web-part"></a>Zpracování událostí ovládacích prvků ve webové části

Přidejte kód, který umožňuje uživateli přidávat kalendáře do zobrazení hlavního kalendáře.

1. Proveďte jednu z následujících sad kroků:

   - V Návrháři dvakrát klikněte **aktualizace** tlačítko.

   - V **vlastnosti** okně **aktualizace** tlačítko, zvolte **události** tlačítko. V **klikněte na tlačítko** vlastnost, zadejte **Button1_Click**a potom stiskněte klávesu Enter.

     Soubor kódu uživatelského ovládacího prvku se otevře v editoru kódu a `Button1_Click` obslužná rutina události se zobrazí. Později přidáte kód pro tuto obslužnou rutinu události.

2. Přidejte následující příkazy do horní části souboru kódu uživatelského ovládacího prvku.

     [!code-vb[SP_VisualWebPart#1](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_VisualWebPart#1](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]

3. Přidejte následující řádek kódu, který `VisualWebPart1` třídy. Tento kód deklaruje ovládací prvek měsíční zobrazení kalendáře.

     [!code-vb[SP_VisualWebPart#2](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#2)]
     [!code-csharp[SP_VisualWebPart#2](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#2)]

4. Nahradit `Page_Load` metodu `VisualWebPart1` třídy následujícím kódem. Tento kód provede následující:

   - Přidá měsíční zobrazení kalendáře do uživatelského ovládacího prvku.

   - Přidá zaškrtávací políčko pro každý seznam kalendáře na webu.

   - Určuje šablonu, která pro každý typ položky, které se zobrazí v zobrazení Kalendář.

     [!code-vb[SP_VisualWebPart#3](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#3)]
     [!code-csharp[SP_VisualWebPart#3](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#3)]

5. Nahradit `Button1_Click` metodu `VisualWebPart1` třídy následujícím kódem. Tento kód přidá položky z každého vybraného kalendáře do zobrazení hlavního kalendáře.

     [!code-vb[SP_VisualWebPart#4](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#4)]
     [!code-csharp[SP_VisualWebPart#4](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#4)]

## <a name="test-the-web-part"></a>Testování webové části

Při spuštění projektu se otevře web služby SharePoint. Webová část je automaticky přidán do Galerie webových částí služby SharePoint. Chcete-li testovat tento projekt, budete provádět následující úlohy:

- Přidejte událost do každého ze dvou samostatných seznamů kalendáře.
- Přidáte webovou část na stránku webových částí.
- Zadejte seznamy, které chcete zahrnout do zobrazení měsíčního kalendáře.

### <a name="to-add-events-to-calendar-lists-on-the-site"></a>Přidání události do seznamů kalendáře na webu

1. V sadě Visual Studio, zvolte **F5** klíč.

     Otevře se web služby SharePoint a [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] panel snadného spuštění se zobrazí na stránce.

2. Na panelu Snadné spuštění v rámci **uvádí**, zvolte **kalendáře** odkaz.

     **Kalendáře** se zobrazí stránka.

     Pokud jste žádný odkaz kalendář zobrazen na panelu Snadné spuštění, zvolte **obsah webu** odkaz. Pokud stránka obsahu webu nezobrazí **kalendáře** položky, vytvořte ji.

3. Na stránce kalendář zvolte den a klikněte na tlačítko **přidat** odkaz u vybraného dne přidejte událost.

4. V **Title** zadejte **událost v kalendáři výchozí**a klikněte na tlačítko **Uložit** tlačítko.

5. Zvolte **obsah webu** propojit a klikněte na tlačítko **přidat aplikaci** dlaždici.

6. Na **vytvořit** zvolte **kalendáře** zadejte název kalendáře a klikněte na tlačítko **vytvořit** tlačítko.

7. Přidejte událost do nového kalendáře, pojmenujte událost **událostí ve vlastním kalendáři**a klikněte na tlačítko **Uložit** tlačítko.

### <a name="to-add-the-web-part-to-a-web-part-page"></a>Chcete-li přidat webové části na stránku webových částí

1. Na **obsah webu** otevřete stránku **stránky webu** složky.

2. Na pásu karet, zvolte **soubory** otevřenou kartou **nový dokument** nabídky a klikněte na tlačítko **stránku webových částí** příkazu.

3. Na **nová stránka webových částí** stránky, zadejte název stránky **SampleWebPartPage.aspx**a klikněte na tlačítko **vytvořit** tlačítko.

     Zobrazí se stránka webové části.

4. V horní oblasti stránky webové části, vyberte **vložit** kartu a klikněte na tlačítko **webové části** tlačítko.

5. Zvolte **vlastní** složky, zvolte **VisualWebPart1** webové části a klikněte na tlačítko **přidat** tlačítko.

     Webová část se zobrazí na stránce. Následující ovládací prvky se zobrazí ve webové části:

    - Měsíční zobrazení kalendáře.

    - **Aktualizace** tlačítko.

    - A **kalendáře** zaškrtávací políčko.

    - A **vlastní kalendář** zaškrtávací políčko.

### <a name="to-specify-lists-to-include-in-the-monthly-calendar-view"></a>Určení seznamů pro zahrnutí do zobrazení měsíčního kalendáře

Ve webové části zadejte kalendáře, které chcete zahrnout do zobrazení měsíčního kalendáře a klikněte na tlačítko **aktualizace** tlačítko.

Události ze všech kalendářů, které jste zadali, se zobrazí zobrazení měsíčního kalendáře.

## <a name="see-also"></a>Viz také:

[Vytvoření webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)  
[Postupy: Vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md)  
[Návod: Vytvoření webové části pro SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)
