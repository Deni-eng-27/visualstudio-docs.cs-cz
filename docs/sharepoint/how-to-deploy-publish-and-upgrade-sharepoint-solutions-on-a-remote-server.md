---
title: "Postupy: nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru | Microsoft Docs"
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
helpviewer_keywords:
- remote deployment [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, remote deployment
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
ms.assetid: d9c67fae-d097-4e26-a2b9-0f72ff800987
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 519f40017fff5dd3241f4563c5a85d0d0d15c01b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server"></a>Postupy: Nasazení, publikování a upgradování řešení služby SharePoint na vzdáleném serveru
  Kromě nasazení řešení služby SharePoint do místního systému, můžete publikovat v izolovaném prostoru řešení služby SharePoint vzdálených lokalit nebo místních webů služby SharePoint. Vzdálený proces publikování zkopíruje soubor WSP server služby SharePoint, nainstaluje řešení a pak umožňuje aktivovat řešení. Rovněž lze upgradovat vzdálenou instalaci řešení služby SharePoint po provedení změn na ni.  
  
## <a name="to-publish-a-sandboxed-sharepoint-solution-to-a-remote-sharepoint-server"></a>Chcete-li publikovat v izolovaném prostoru řešení služby SharePoint na vzdálený server služby SharePoint  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídky v izolovaném prostoru projektu služby SharePoint, kterou chcete publikovat a potom vyberte **publikovat**.  
  
2.  V **publikovat** dialogovém okně vyberte **publikovat na webu služby SharePoint** možnost tlačítko a potom zadejte adresu URL online publikování webu, například v následujícím příkladu: **https:// mytestsite.SharePoint.microsoftonline.com**.  
  
3.  Vyberte **otevřete řešení Galerie stránku v prohlížeči po publikování** tlačítko Možnosti zobrazíte seznam řešení v **řešení Galerie** stránka po publikování.  
  
4.  Vyberte **publikovat** tlačítko.  
  
5.  Pokud se vyžaduje ověření uživatele, přihlaste se ke vzdálenému serveru.  
  
     V sadě Visual Studio se zobrazí průběh publikování **výstup** okno. Po dokončení tohoto procesu je soubor řešení (WSP) je nainstalován na vzdáleném serveru SharePoint. Nicméně je nutné stále ho aktivovat před jeho použitím ve službě SharePoint.  
  
6.  Na **řešení Galerie** vyberte aplikace SharePoint a pak na pásu karet, zvolte **aktivovat** tlačítko.  
  
7.  V **aktivovat řešení** dialogové okno, na pásu karet, vyberte **aktivovat** tlačítko znovu.  
  
     **Stav** sloupec **řešení Galerie** stránky označuje, že je aplikace aktivní.  
  
## <a name="to-upgrade-a-sandboxed-sharepoint-solution-on-a-remote-sharepoint-server"></a>K upgradu v izolovaném prostoru řešení služby SharePoint na vzdáleném serveru SharePoint  
 Pokud v izolovaném prostoru řešení služby SharePoint je již publikována na vzdáleném serveru, následující postup umožňuje upgradovat po provedení změn na aplikaci v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
1.  Přejmenujte balíček služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Chcete-li to provést, v **Průzkumníku řešení** otevřete balíček. Zobrazí se v **balíček Průzkumníka**.  
  
2.  V **balíček Průzkumníka**v **název** pole, změňte název balíčku na jedinečný název.  
  
3.  Uložte projekt.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **publikovat**.  
  
5.  V **publikovat** dialogovém okně vyberte **publikovat na webu služby SharePoint** možnost tlačítko a poté, pokud chybí adresa URL pro vzdálený server, kde je uložena řešení, zadejte její název.  
  
6.  Vyberte **otevřete řešení Galerie stránku v prohlížeči po publikování** tlačítko Možnosti zobrazíte seznam řešení v **řešení Galerie** stránka po publikování.  
  
7.  Vyberte **publikovat** tlačítko.  
  
8.  Pokud se vyžaduje ověření uživatele, přihlaste se ke vzdálenému serveru.  
  
     Pokud jste přihlášení ke vzdálenému serveru nedávno, nemusí být vyžaduje ověřování.  
  
     Pokud starší verze aplikace, která má stejný název se stále nachází na serveru SharePoint, obdržíte chybu, která balíček se stejným názvem již existuje v serveru SharePoint. Balíček je třeba přejmenovat na jedinečný název před publikováním.  
  
9. Zvolte Nová aplikace ve službě SharePoint a pak na pásu karet **Upgrade** tlačítko.  
  
10. V **upgradovat řešení** dialogové okno, na pásu karet, vyberte **Upgrade** tlačítko znovu. **Stav** sloupec **Galerie řešení** stránky by měl nyní označení, že je aplikace aktivní.  
  
     Stará verze řešení je deaktivována, upgradovaná data udržovaná z původního řešení novou verzi řešení a nového řešení je aktivována ve službě SharePoint.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nasazení a publikování řešení služby SharePoint na místní web služby SharePoint](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)   
 [Vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)   
 [Postupy: přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [Postupy: Přidání nebo odebrání funkcí a položek z balíčku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  