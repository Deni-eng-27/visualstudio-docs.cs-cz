---
title: 'Postupy: Vytvoření knihovny aktivit | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ce02d639f6fcd3040566a2c279713c046f9c6ead
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068092"
---
# <a name="how-to-create-an-activity-library"></a>Postupy: Vytvoření knihovny aktivit
Vlastní aktivity se používají k modelování vašich konkrétních obchodních procesů v pracovním postupu. Šablona knihovny aktivit v [!INCLUDE[vs2010](../includes/vs2010-md.md)] má byla poskytnutá těmto osobám umožňují vytvářet tyto vlastní aktivity vizuálně pomocí [!INCLUDE[wfd1](../includes/wfd1-md.md)].  
  
### <a name="to-create-a-workflow-activity-library"></a>K vytvoření knihovny aktivit pracovních postupů  
  
1. Spustit [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2. Na **souboru** nabídky, přejděte k **nový**a pak vyberte **projektu...** .  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
3. V **typy projektů** vyberte **pracovního postupu** buď z **Visual C#** projekty nebo **jazyka Visual Basic** seskupení v závislosti na vaší preferovaný jazyk.  
  
4. V **šablony** vyberte **knihovny aktivit**.  
  
5. V **název** pole, zadejte popisný název pro váš projekt k usnadňují identifikaci.  
  
6. V **umístění** , zadejte v adresáři, ve kterém chcete projekt uložit nebo klikněte na tlačítko **Procházet** přejít k němu.  
  
7. V **řešení** pole, zadejte popisný název pro vaše řešení a pak klikněte na tlačítko **OK**.  
  
    > [!NOTE]
    >  Pokud chcete přidat Konzolová aplikace pracovního postupu do existujícího řešení, otevřete toto řešení [!INCLUDE[vs2010](../includes/vs2010-md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníka řešení**a vyberte **přidat**, pak  **Nový projekt...** Chcete-li otevřít **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.  
  
8. Šablona projektu vytvoří definici aktivity v XAML. [!INCLUDE[wfd1](../includes/wfd1-md.md)] Otevře a zobrazí na plátně pro vaše vlastní aktivity.  
  
9. Přetáhněte aktivitu z **nástrojů** na návrhovou plochu se zahrnuje do vaší vlastní aktivitě.  
  
    > [!CAUTION]
    >  V těle vaší vlastní aktivitě; jsou povoleny pouze jednu podřízenou aktivitu avšak podřízené aktivity mohou být složené aktivity, například <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Flowchart> aktivity.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření aktivity](http://msdn.microsoft.com/library/c09b1e99-21b5-4d96-9c04-ec31db3f4436)   
 [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)