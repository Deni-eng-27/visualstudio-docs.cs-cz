---
title: "Postupy: nastavení příkazů nasazení služby SharePoint | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, deploying
ms.assetid: 289c8c33-a603-434e-889f-a0d0a1736ecb
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 65c67972dddedcd05338d793883b2dcba0789d48
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Postupy: Nastavení příkazů nasazení služby SharePoint
  Proces nasazení můžete přizpůsobit nastavení příkazy před nasazením a po nasazení. Tyto příkazy spustit před a po dalších akcí nasazení při ladění řešení služby SharePoint v sadě Visual Studio.  
  
### <a name="to-add-a-pre-deployment-command"></a>Chcete-li přidat příkaz před nasazením  
  
1.  Na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **před nasazením příkazového řádku** textové pole, zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Například pro zobrazení seznamu obsah adresáře, než bude dokončeno nasazení, zadejte **dir**.  
  
### <a name="to-add-a-post-deployment-command"></a>Chcete-li přidat příkaz po nasazení  
  
1.  Na řádku nabídek zvolte **projektu**, *ProjectName***vlastnosti**.  
  
2.  Vyberte **SharePoint** kartě.  
  
3.  V **po nasazení příkazového řádku** text zadejte MS-DOS nebo MSBuild příkazy k přizpůsobení tohoto kroku.  
  
     Po dokončení nasazení, zobrazit obsah adresáře, zadejte **dir**. Chcete-li proměnnou MSBuild zkopírujte sestavení z adresáře sestavení, zadejte **zkopírujte $(TargetPath) c:\DeploymentDirectory**.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  