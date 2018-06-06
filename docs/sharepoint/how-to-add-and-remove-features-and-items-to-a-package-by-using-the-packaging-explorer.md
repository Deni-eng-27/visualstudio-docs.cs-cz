---
title: 'Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f8c838880dd7d7e7adfe080541f1419bd4651ff3
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767439"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků
  Pokud chcete nakonfigurovat balíček pro nasazení SharePoint – položky a funkce, můžete použít Průzkumníku balíčků. SharePoint – položky projektu a funkcí můžete upravit v souboru WSP.  
  
 Alternativně můžete použít Návrháře balení k zobrazení a změnit pořadí funkce, které chcete změnit pořadí aktivace. Další informace najdete v tématu [postupy: Přidání nebo odebrání funkcí a položek z balíčku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).  
  
## <a name="opening-the-packaging-explorer"></a>Otevírání Průzkumníku balíčků  
 Následující postup slouží k otevření Průzkumníku balíčků, pokud má vaše řešení sady Visual Studio alespoň jeden projektu služby SharePoint. Alternativně Průzkumníku balíčků se automaticky otevře při prohlížení návrháře funkce nebo balíčku. Když zavřete všechny funkce a balíku návrhářů, zavře se také Průzkumníku balíčků.  
  
#### <a name="to-open-the-packaging-explorer"></a>Chcete-li otevřít Průzkumníku balíčků  
  
1.  Na řádku nabídek zvolte **zobrazení** > **ostatní okna** > **Průzkumníku balíčků**.  
  
     **Průzkumníku balíčků** se zobrazí v **sada nástrojů**.  
  
## <a name="adding-a-feature-to-a-package"></a>Přidání funkce do balíčku  
 Do balíčku můžete přidat nové funkce pomocí Průzkumníku balíčků.  
  
#### <a name="to-add-a-sharepoint-feature"></a>Chcete-li přidat funkce služby SharePoint
  
1.  Otevřete **Průzkumníku balíčků**, otevřete místní nabídky projektu a zvolte **přidat funkce**.  
  
#### <a name="to-move-an-existing-sharepoint-feature"></a>Chcete-li přesunout existující funkce služby SharePoint  
  
1.  Otevřete **Průzkumníku balíčků**a poté proveďte jednu z následujících kroků:  
  
    -   Přetáhněte **funkce** z jednoho projektu do jiného projektu.  
  
    -   Otevřete místní nabídky pro funkci, zvolte **Vyjmout**, otevřete místní nabídku pro projekt, do které chcete přesunout funkci a potom vyberte **vložení**.  
  
    > [!NOTE]  
    >  Tento postup použijte, pokud máte více než jeden projektu služby SharePoint ve vašem řešení.  
  
## <a name="validating-a-feature-or-package"></a>Funkce nebo balíčku  
 S těmito soubory můžete identifikovat potenciální problémy s funkcí služby SharePoint a balíčky. Upozornění a chyb se zobrazí v okně výstupu a v okně Seznam chyb.  
  
#### <a name="to-validate-a-sharepoint-feature-or-package"></a>Ověřit funkce služby SharePoint nebo balíčku
  
1.  Otevřete **Průzkumníku balíčků**.  
  
2.  Otevřete místní nabídku pro funkci nebo balíčku a zvolte **ověřením**.  
  
## <a name="see-also"></a>Viz také:
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
