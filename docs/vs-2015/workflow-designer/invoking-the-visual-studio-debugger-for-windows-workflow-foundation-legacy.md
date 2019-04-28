---
title: Vyvolání ladicího programu pro programovací model Windows Workflow Foundation (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 82532fc2864bcb4c19b0cf122e60fd9a64b2dbf9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62952916"
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Vyvolání ladicího programu sady Visual Studio pro programovací model Windows Workflow Foundation (starší verze)
Toto téma popisuje, jak používat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladicí program k ladění [!INCLUDE[wf](../includes/wf-md.md)] aplikací ve starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Použijte starší [!INCLUDE[wfd2](../includes/wfd2-md.md)] potřeba cílit na platformu [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].

 Obecně platí ladění starších verzí pracovních postupů stejným způsobem, jako ladíte programy napsané v jiných programovacích jazycích sady Visual Studio. Můžete spustit [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] ladicího programu pro Windows Workflow Foundation následujícími způsoby:

- Vyberte **připojit k procesu** na **ladění** nabídky vybrat běžící instance pracovního postupu z procesy k dispozici.

- Stisknutím klávesy **F5** spouštění instance pracovního postupu, nebo aby kontinuálně běžely, jakmile dosáhne zarážky.

## <a name="stepping-through-code"></a>Krokování kódem
 Ladicí program podporuje jeden z nejběžnějších postupů ladění, krokování, které spouští jeden řádek kódu v čase. Existují tři příkazy krokování kódem:

- **Krok v**: Můžete krokovat s vnořením aktivity pomocí **F11**. Ladicí program do libovolné obslužné rutiny, která je definována. Pokud není definována žádná obslužná rutina, Krokovat přes aktivity nebo pomocí složených aktivit, které obsahují další aktivity, přejdete na první spouštěné aktivity. Krokování s vnořením do kódu obslužné rutiny z Návrháře se nepodporuje pro následující činnosti: **Aktivita typu IfElseActivity**, **aktivita typu WhileActivity**, **aktivitou skupiny ConditionedActivityGroup**, nebo **aktivitou typu ReplicatorActivity**. Chcete-li ladit obslužné rutiny související s tyto aktivity, je nutné umístit explicitní zarážky v kódu.

- **Krokovat s Vystoupením**: Můžete krokovat z aktivity pomocí **Shift-F11**. Krokování mimo aktivitu spouští aktuální aktivitu a jejich na stejné úrovni aktivity do konce. Ladicí program zastaví se na nadřazený prvek aktuální aktivity. Při procházení z obslužné rutiny kód, ladicí program přeruší na aktivitu, ke kterému je přidružené obslužnou rutinu.

- **Krok přes**: Můžete krokovat přes aktivity pomocí **F10**. Při krokování přes složené aktivity. ladicí program přeruší na první spustitelný podřízený složené aktivity. Při krokování přes bez složeného, například **CodeActivity** aktivity, ladicí program provede aktivitu a jeho přidruženými obslužnými rutinami a zalomení na další aktivity. Pokud je aktivita, která se spustí poslední podřízenou aktivitou ve složených aktivit, pak po spuštění, ladicí program přeruší na Nadřazená aktivita.

## <a name="attaching-to-a-process"></a>Připojení k procesu
 Chcete-li ladit pracovní postup připojení k procesu, vyberte procesu k dispozici z **procesy k dispozici** pole se seznamem v **připojit k procesu** dialogové okno. Pokud **automatické: Kód pracovního postupu** se nezobrazuje **připojit k** text a potom klikněte na tlačítko **vyberte**. V **vybrat typ kódu** dialogové okno, klikněte na tlačítko **ladit tyto typy kódu** a vyberte **pracovního postupu**. Pak klikněte na tlačítko **OK** a klikněte na tlačítko **připojit**.

## <a name="debugging-with-f5"></a>Ladění pomocí F5
 Pokud aplikace hostitele pracovního postupu a pracovní postup knihovny DLL jsou umístěny v různých projektech Visual Studio, například při použití knihovny aktivit pracovních postupů, je nutné nastavit pracovní postup projektu knihovny DLL jako spouštěcího projektu řešení sady Visual Studio pro ladění pracovního postupu pomocí **F5**. Musíte taky nastavit cestu k hostitelské aplikace v projektu knihovny DLL pracovního postupu **externí program Start** vlastnost.

 V Průzkumníku řešení nastavte projekt po spuštění, klikněte pravým tlačítkem na název projektu a vyberte **nastavit jako spouštěný projekt**. Nastavit cestu k hostiteli v **externí program Start** vlastnost, dvakrát klikněte na projekt pracovního postupu **vlastnosti** uzel v Průzkumníku řešení a vyberte **ladění** Karta. V části **spustit akci**vyberte **externí program Start** a zadejte cestu k souboru .exe, který je hostitelem pracovního postupu, který chcete ladit.

 Pokud hostitelská aplikace je nastaven jako spouštěný projekt, je vyvolána pouze ladicí program pro Visual Studio pro ladění. [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] není vyvolána, ladicí program pro Windows Workflow Foundation. Pokud se používá ladicí program sady Visual Studio, jsou volání pouze C# nebo Visual Basic kódu zarážky; nejsou dosažení zarážky nastavené v Návrháři pracovních postupů. Například zarážky, které jste nastavili na <xref:System.Workflow.Activities.ParallelActivity> dosažení aktivit v návrháři, pokud [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] se používá ladicí program pro Windows Workflow Foundation, ale není při použití ladicího programu sady Visual Studio.

## <a name="see-also"></a>Viz také
 [Postupy: Nastavení zarážek v pracovních postupech (starší verze)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md) [ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)