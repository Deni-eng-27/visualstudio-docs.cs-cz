---
title: "Postupy: vytvoření knihovny stavu počítače pracovního postupu (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- projects, state machine workflow library
- state machine workflow libraries
- workflows, state machine workflow library
ms.assetid: 5bd68c6e-6a98-47d9-826d-9bb7a4fd72f8
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 73fe219a3047758f66dbff47e59031adb1de9258
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-state-machine-workflow-library-legacy"></a>Postupy: vytvoření knihovny stavu počítače pracovního postupu (zastaralé)
Postupujte podle těchto kroků můžete vytvořit projekt knihovny pracovního postupu stav počítače pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] poskytované [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
### <a name="to-create-a-state-machine-workflow-library-project"></a>Vytvoření projektu knihovny stavu počítače pracovního postupu  
  
1.  Spuštění sady Visual Studio.  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.  
  
     **Nový projekt** otevře se dialogové okno.  
  
3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.  
  
    > [!NOTE]
    >  Výchozí možnost v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] je **rozhraní .NET Framework 4**. Tato možnost slouží k vytvoření [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] a nepoužívá návrháře starší verze.  
  
4.  V **typy projektů** podokně, vyberte Visual C# nebo Visual Basic (v části **jiné jazyky**) a potom vyberte **pracovního postupu**.  
  
5.  V **šablony** podokně, vyberte **stavu počítače pracovního postupu knihovny**.  
  
6.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.  
  
7.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.  
  
     Pokud chcete vytvořit pro projekt adresář řešení, vyberte **vytvořit adresář pro řešení** zaškrtněte políčko a zadejte název do pole **název řešení** pole.  
  
8.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření projektů pracovního postupu starší verze](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Pracovní postupy stavového stroje](/dotnet/framework/windows-workflow-foundation/state-machine-workflows)