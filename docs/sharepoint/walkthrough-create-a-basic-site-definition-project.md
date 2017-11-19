---
title: "Návod: Vytvoření základního projektu definice webu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
ms.assetid: b0df5b0e-5fa0-43d8-a339-6d92f1276764
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9bea8fec27b0d53fb1cfe3405d39d271a93f5a8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-basic-site-definition-project"></a>Postupy: Vytvoření základního projektu definice webu
  Tento návod ukazuje, jak vytvořit definici základní lokality, který obsahuje vizuální webová část s některé ovládací prvky na něm. V zájmu přehlednosti visual webovou část, kterou vytvoříte má několik ovládacích prvků. Můžete však vytvořit sofistikovanější definice webů služby SharePoint, které obsahovaly další funkce.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytvoření definice webu pomocí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] šablona projektu.  
  
-   Vytvoření webu služby SharePoint pomocí definice webu ve službě SharePoint.  
  
-   Přidávání do řešení visual webové části.  
  
-   Přizpůsobení default.aspx stránka přidáním nové visual webové části.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu požadavky pro vývoj řešení služby SharePoint.  
  
-   Visual Studio.  
  
## <a name="creating-a-site-definition-solution"></a>Vytvoření řešení definice webu  
 Nejprve vytvořte projektu definice webu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-create-a-site-definition-project"></a>Vytvoření projektu definice webu  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**. Pokud vaše IDE nastaven pro použití nastavení vývoj jazyka Visual Basic, v řádku nabídek, zvolte **soubor**, **nový projekt**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  Rozbalte položku **Visual C#** uzlu nebo **jazyka Visual Basic** uzlu, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
3.  V **šablony** seznam, vyberte **projektu služby SharePoint 2010** šablony.  
  
4.  V **název** zadejte **TestSiteDef**a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
5.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte adresu URL pro web služby SharePoint, kam chcete ladit definici lokality nebo použijte výchozí umístění (http://*systémový název*/).  
  
6.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** tlačítko.  
  
     Všechny projekty definice lokality musí být nasazený jako řešení ve farmách. Další informace o řešení v izolovaném prostoru a řešení ve farmách najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Vyberte **Dokončit** tlačítko.  
  
     Projekt se objeví v **Průzkumníku řešení**.  
  
8.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
9. V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
10. V **šablony** podokně, vyberte **definici lokality** šablony, ponechejte **název** jako **SiteDefinition1**a potom vyberte  **Přidat** tlačítko.  
  
## <a name="create-a-visual-web-part"></a>Vytvoření vizuální webové části  
 Dále vytvořte visual webovou část se objevily na hlavní stránce definici lokality.  
  
#### <a name="to-create-a-visual-web-part"></a>Vytvoření vizuální webové části  
  
1.  V **Průzkumníku řešení**, vyberte **zobrazit všechny soubory** tlačítko.  
  
2.  Vyberte **SiteDefinition1** uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
3.  Rozbalte položku **Visual C#** uzlu nebo **jazyka Visual Basic** uzlu, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
4.  V seznamu šablon, vyberte **Visual webovou část** šablony, nechejte výchozí název VisualWebPart1 a potom vyberte **přidat** tlačítko.  
  
     Otevře se soubor VisualWebPart1.ascx.  
  
5.  V dolní části VisualWebPart1.ascx, přidejte následující kód k přidávání tři ovládacích prvků formuláře: textové pole, tlačítka a štítku:  
  
    ```  
    <table>  
      <tr>  
        <td>  
          <asp:TextBox runat="server" ID="tbName"></asp:TextBox>  
        </td>  
        <td>  
          <asp:Button runat="server" ID="btnSubmit" Text = "Change Label Text" OnClick="btnSubmit_Click"></asp:Button>  
        </td>  
        <td>  
          <asp:Label runat="server" ID="lblName"></asp:Label>  
        </td>  
      </tr>  
    </table>  
    ```  
  
6.  V části VisualWebPart1.ascx, otevřete soubor VisualWebPart1.ascx.cs (pro [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]) nebo VisualWebPart1.ascx.vb (pro [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) a poté přidejte následující kód:  
  
     [!code-vb[SP_SimpleSiteDef#1](../sharepoint/codesnippet/VisualBasic/testsitedefvb/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_SimpleSiteDef#1](../sharepoint/codesnippet/CSharp/testsitedef/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]  
  
     Tento kód přidá funkce pro webové části kliknutí na tlačítko.  
  
## <a name="add-the-visual-web-part-to-the-default-aspx-page"></a>Přidání vizuální webové části na výchozí stránku ASPX  
 V dalším kroku přidáte visual webovou část na stránku ASPX výchozí definici lokality.  
  
#### <a name="to-add-a-visual-web-part-to-the-default-aspx-page"></a>Přidání vizuální webové části na výchozí stránku ASPX  
  
1.  Otevřete stránku default.aspx a potom přidejte následující řádek v části `WebPartPages` značky:  
  
    ```  
    <%@ Register Tagprefix="MyWebPartControls" Namespace="TestSiteDef.VisualWebPart1" Assembly="$SharePoint.Project.AssemblyFullName$" %>  
    ```  
  
     Tento řádek přidruží název MyWebPartControls webové části a jeho kód. *Namespace* obor názvů, který se používá v souboru kódu VisualWebPart1.ascx odpovídá parametru.  
  
2.  Po `</asp:Content>` elementu, nahraďte celou `ContentPlaceHolderId="PlaceHolderMain"` části a jeho obsah následujícím kódem:  
  
    ```  
    <asp:Content ID="Content1" ContentPlaceHolderId="PlaceHolderMain" runat="server">  
        <MyWebPartControls:VisualWebPart1 runat="server" />      
    </asp:Content>  
    ```  
  
     Tento kód vytvoří odkaz na visual webovou část, kterou jste vytvořili dříve.  
  
3.  V **Průzkumníku řešení**, otevřete místní nabídku pro **SiteDefinition1** uzel a potom zvolte **nastavit jako položku při spuštění**.  
  
## <a name="deploy-and-run-the-site-definition-solution"></a>Nasazení a spuštění řešení definice webu  
 V dalším kroku nasaďte projekt do služby SharePoint a spusťte projekt.  
  
#### <a name="to-deploy-and-run-the-site-definition"></a>Nasazení a spuštění definice webu  
  
-   Na řádku nabídek zvolte **sestavení**, **nasazení TestSiteDef**.  
  
-   Zvolte klávesy F5.  
  
     Visual Studio kompilovaný kód, přidá jeho funkce, všechny soubory balíčků do souboru (WSP) řešení služby SharePoint a nasadí WSP soubor na Server služby SharePoint. SharePoint pak nainstaluje soubory a potom aktivuje funkce.  
  
## <a name="create-a-site-based-on-the-site-definition"></a>Vytvoření webu na základě definice webu  
 Dále vytvořte lokalitu pomocí nové definice webu.  
  
#### <a name="to-create-a-site-by-using-the-site-definition"></a>Vytvoření webu s použitím definice webu  
  
1.  Na webu služby SharePoint zobrazí se stránka Nový web služby SharePoint.  
  
2.  V **název a popis** zadejte **názvem nový web** název a popis webu.  
  
3.  V **adresa webu** zadejte **Nový_server** v **název adresy URL** pole.  
  
4.  V **šablony** zvolte **SharePoint přizpůsobení** kartě.  
  
5.  V **vyberte šablonu** vyberte **SiteDefinition1**.  
  
6.  Nechte ostatní nastavení na jejich výchozí hodnoty a potom vyberte **vytvořit** tlačítko.  
  
     Zobrazí se nové lokality.  
  
## <a name="test-the-new-site"></a>Testování nového webu  
 V dalším kroku otestujte nové lokality k ověření, zda funguje správně.  
  
#### <a name="to-test-the-new-site"></a>Otestování nového webu  
  
-   Na výchozí stránky ASPX, zadejte text a potom vyberte **Text popisku změnu** tlačítko vedle textového pole.  
  
     Text se zobrazí v popisku na pravé straně tlačítka.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  