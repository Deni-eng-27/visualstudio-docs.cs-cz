---
title: 'Postupy: Vytvoření aplikace služby pracovního postupu WCF | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9bf941babd943c6856809a13de847b62745b2056
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72605016"
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>Postupy: Vytvoření aplikace služby pracovního postupu WCF
[!INCLUDE[indigo1](../includes/indigo1-md.md)] aplikace služby pracovního postupu jsou distribuované komunikační služby, které předávají zprávy mezi klienty a mezi nimi napříč hranicemi procesů. Implementace kontraktu služby na straně služby se provádí deklarativně prostřednictvím aktivit pracovních postupů v [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] způsobem podobným starším službám pracovního postupu v .NET Framework 3,5.

### <a name="to-create-a-wcf-workflow-service-application"></a>Vytvoření aplikace služby pracovního postupu WCF

1. Spusťte [!INCLUDE[vs2010](../includes/vs2010-md.md)].

2. V nabídce **soubor** přejděte na příkaz **Nový**a vyberte možnost **projekt...** .

     Otevře se dialogové okno **Nový projekt** .

3. V podokně **Nainstalované šablony** vyberte možnost **WCF** nebo **pracovní postup** ze skupin **vizuálů C#**  nebo **Visual Basic** v závislosti na zvoleném jazyce.

4. V prostředním podokně vyberte **aplikace služby pracovního postupu WCF**.

5. Do pole **název** zadejte popisný název projektu, který usnadňuje identifikaci.

6. Do pole **umístění** zadejte adresář, do kterého chcete uložit projekt, nebo klikněte na tlačítko **Procházet** a přejděte na něj.

7. V poli **řešení** vyberte možnost vytvořit nové řešení a pak klikněte na tlačítko **OK**.

    > [!NOTE]
    > Pokud chcete přidat konzolovou aplikaci pracovního postupu do existujícího řešení, otevřete toto řešení v [!INCLUDE[vs2010](../includes/vs2010-md.md)], klikněte pravým tlačítkem na řešení v **Průzkumník řešení**a vyberte **Přidat**a **Nový projekt...** pro otevření dialogového okna **Nový projekt** . Pokračujte postupem uvedeným výše v tomto postupu.

8. Šablona projektu vytvoří definici služby jako XAML. @No__t_0 se otevře v zobrazení Návrh s aktivitou <xref:System.Activities.Statements.Sequence>, která obsahuje sadu <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivit.

## <a name="see-also"></a>Viz také
 [Postupy: vytvoření aktivity](https://msdn.microsoft.com/library/c09b1e99-21b5-4d96-9c04-ec31db3f4436) [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)