---
title: 'Postupy: lokalizace značek ASPX | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- localizing XML [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b43a8833ea84c4f6d191200bcf3af80815deb03a
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-localize-aspx-markup"></a>Postupy: Lokalizace značek ASPX
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránky (.aspx) obvykle používají pevně řetězcové hodnoty. Chcete-li tyto řetězce pro lokalizaci, je nahradíte výrazy, které odkazují na lokalizované prostředky.  
  
## <a name="localizing-aspx-markup"></a>Lokalizace značek ASPX  
  
#### <a name="to-localize-aspx-markup"></a>Chcete-li lokalizace značek ASPX  
  
1.  Přidat soubory samostatné prostředků: jeden pro výchozí jazyk a jeden pro jednotlivé lokalizované jazyk.  
  
     Pokud jsou lokalizace pouze značek a kódu není, přidejte položku globální prostředky souboru projektu. Pokud jsou lokalizace kódu a kódu, přidejte položka projektu souboru prostředků.  
  
    1.  Chcete-li přidat soubor globální prostředky v **Průzkumníku řešení**, otevřete místní nabídku pro položky projektu služby SharePoint a potom zvolte **přidat**, **novou položku**. V části služby SharePoint **2010** uzlu, vyberte **globální souboru prostředků** šablony.  
  
    2.  Přidání souboru prostředků v **Průzkumníku řešení**, otevřete místní nabídku pro položky projektu služby SharePoint a potom zvolte **přidat**, **novou položku**. V části buď **jazyka Visual Basic** nebo **Visual C#** uzlu, vyberte **souboru prostředků** šablony.  
  
    > [!NOTE]  
    >  Nezapomeňte přidat soubory prostředků do položky projektu služby SharePoint k povolení vlastnosti typu nasazení. Tato vlastnost se vyžaduje později v tomto postupu. Pokud vaše řešení nemá položky projektu služby SharePoint, můžete přidat prázdný projekt SharePoint a odebrat jeho výchozí Elements.xml soubor.  
  
2.  Zadejte název zvoleného spolu s příponou RESX, jako je například MyAppResources.resx souboru prostředků jazyka výchozí. Použijte stejný základní název pro každý soubor lokalizovaný prostředek, ale přidat jazykovou verzi [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Například název němčině lokalizovaný prostředek MyAppResources.de DE.resx.  
  
3.  Změňte hodnotu **typ nasazení** vlastnost souborů prostředků se **AppGlobalResource** způsobit pro nasazení do složky App_GlobalResources serveru.  
  
4.  Pokud používáte prostředky k lokalizaci kód kromě značek ASPX, ponechte hodnotu **akce sestavení** vlastnosti každého souboru jako **vložený prostředek**. Pokud používáte pouze k lokalizaci značek soubory prostředků, můžete volitelně změňte hodnotu vlastnosti souborů pro **obsahu**. Další informace najdete v tématu [lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md).  
  
5.  Otevřete soubor každý prostředek a přidejte lokalizované řetězce, pomocí stejné ID řetězce do každého souboru.  
  
6.  V [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] kód pro stránky ASPX nebo ovládací prvek, nahraďte pevně řetězce s hodnotami, které použijte následující formát:  
  
    ```aspx-csharp  
    <%$Resources:Resource File Name, String ID%>  
    ```  
  
     Například k lokalizaci text pro ovládací prvek popisek na stránku aplikace, změníte:  
  
    ```aspx-csharp  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>  
    </asp:Content>  
    ```  
  
     až  
  
    ```aspx-csharp  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>  
    </asp:Content>  
    ```  
  
7.  Zvolte klávesy F5 sestavení a spuštění aplikace.  
  
8.  Ve službě SharePoint změňte z výchozí jazyk zobrazení.  
  
     Lokalizované řetězce se zobrazí v aplikaci. Pokud chcete zobrazit lokalizované prostředky, musí mít serveru SharePoint jazyková sada nainstalovaná odpovídající jazykové verze souboru prostředků.  
  
## <a name="see-also"></a>Viz také  
 [Lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md)   
 [Postupy: lokalizace funkce](../sharepoint/how-to-localize-a-feature.md)   
 [Postupy: Přidání zdrojového souboru](../sharepoint/how-to-add-a-resource-file.md)   
 [Postupy: Lokalizace kódu](../sharepoint/how-to-localize-code.md)  
  
  