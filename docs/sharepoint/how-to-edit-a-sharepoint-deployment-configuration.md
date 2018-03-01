---
title: "Postupy: Úprava konfigurace nasazení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.DeploymentConfig
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 4e5e65e82910239b596e4b19f2ea1fa1f357266c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-edit-a-sharepoint-deployment-configuration"></a>Postupy: Úprava konfigurace nasazení služby SharePoint
  Můžete vytvořit konfiguraci nasazení nebo změnit existující konfiguraci nasazení. Například můžete spustit jeden krok nebo změnit pořadí kroků v procesu nasazení. Můžete k vytvoření nebo úprava konfigurace nasazení, protože nejde změnit konfiguraci předdefinované a přidané prostřednictvím kódu programu.  
  
## <a name="creating-a-sharepoint-deployment-configuration"></a>Vytvoření konfigurace nasazení služby SharePoint  
  
#### <a name="to-create-a-sharepoint-deployment-configuration"></a>Pro vytvoření konfigurace nasazení služby SharePoint  
  
1.  V **Průzkumníku řešení**, zvolte projektu služby SharePoint a potom na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Na **SharePoint** , zvolte **nový** tlačítko.  
  
     **Přidat novou konfiguraci nasazení** zobrazí se dialogové okno.  
  
3.  V **název** textové pole, zadejte název pro konfiguraci nasazení.  
  
4.  V **dostupné kroky nasazení** podokně vyberte kroky, které chcete přidat do konfigurace nasazení, vyberte (**>**) tlačítko a potom vyberte **OK** tlačítko.  
  
    > [!NOTE]  
    >  Pokud jste nakonfigurovali před nasazením příkaz nebo příkaz po nasazení, tyto kroky spustit pouze v případě, že je přidáte do konfigurace přizpůsobená nasazení.  
  
## <a name="changing-the-active-deployment-configuration"></a>Změna konfigurace nasazení služby Active  
  
#### <a name="to-change-the-active-deployment-configuration"></a>Chcete-li změnit konfiguraci aktivní nasazení  
  
1.  V **Průzkumníku řešení**, zvolte projektu služby SharePoint a potom na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **aktivní konfigurace nasazení** seznam pole, klikněte na název konfigurace nasazení, který chcete použít.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  