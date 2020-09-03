---
title: Ladění pracovních postupů pomocí návrháře postupu provádění
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Workflow Designer [WFD], debugging workflows
- Workflow Designer [WFD], debugging workflows
ms.assetid: d71308cf-d464-4536-8711-0d0a8eadb255
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b8de1ff9875d175c956a45b87d459d0943e783c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75597058"
---
# <a name="debug-workflows-with-the-workflow-designer"></a>Ladění pracovních postupů pomocí Návrhář postupu provádění

**Návrhář postupu provádění** poskytuje možnost ladit pracovní postupy a vlastní aktivity. Proces a chování jsou podobné tomu jako výchozí ladicí program sady Visual Studio.

## <a name="invoke-the-workflow-debugger"></a>Vyvolat ladicí program pracovního postupu

Obecně je potřeba ladit pracovní postupy stejně jako při ladění programů napsaných v jiných programovacích jazycích sady Visual Studio. Ladicí program pracovního postupu můžete spustit následujícími způsoby:

- V nabídce **ladění** vyberte **připojit k procesu** a vyberte běžící hostitelský proces pro vaši instanci pracovního postupu. Tento postup je stejný jako připojení k hostitelskému procesu ve spravovaném kódu.

- Stiskněte klávesu **F5** ke spuštění instance pracovního postupu nebo ke spuštění i po dosažení zarážky.

- Použijte vzdálené ladění. Informace o použití vzdáleného ladění naleznete v tématu [How to: Enable Remote Debugging](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

   > [!NOTE]
   > Pokud je aplikace pracovního postupu cílena na architekturu x86 a je hostována na počítači s 64 bitovým operačním systémem, pak vzdálené ladění nebude fungovat, pokud není nainstalována aplikace Visual Studio na vzdáleném počítači nebo že cíl pro aplikaci pracovního postupu se změní na **Libovolný procesor**.

## <a name="step-through-code"></a>Krokovat kód

- **Krok**dovnitř: krokování na aktivitu stisknutím klávesy **F11**. Ladicí program popisuje všechny definované obslužné rutiny. Pokud není definována žádná obslužná rutina, můžete krokovat s aktivitou nebo se složenými aktivitami, které obsahují další aktivity, a krokovat s první vykonávanou aktivitou.

- **Krok ven:** Krok ven z aktivity stisknutím klávesy **SHIFT** + **F11**. Krokování mimo aktivitu spustí aktuální aktivitu a všechny její aktivity na stejné úrovni jako dokončené. Ladicí program se pak rozdělí na nadřazený objekt aktuální aktivity. Při rozkrokování z obslužné rutiny kódu se ladicí program ukončí u aktivity, ke které je přidružena obslužná rutina.

- **Krok za**: krok po aktivitě stisknutím klávesy **F10**. Při krokování nad složenou aktivitou se ladicí program ukončí u prvního spustitelného prvku složené aktivity. Při rozkrokování mimo nesložené, jako je <xref:System.Activities.Statements.Assign> aktivita, provede ladicí program aktivitu a její přidružené obslužné rutiny a přeruší se na další aktivitu. Pokud je spuštěná aktivita poslední podřízená aktivita v složené aktivitě, potom po provedení dojde k přerušení ladicího programu u nadřazené aktivity.

## <a name="debug-with-f5"></a>Ladění pomocí F5

Pokud vytváříte konzolovou aplikaci pracovního postupu, stačí stisknout klávesu **F5** a zahájit tak ladění aplikace a pracovního postupu. Pokud vytváříte knihovnu aktivit sami, musíte jako spouštěný projekt zadat spustitelnou aplikaci hostitele. Chcete-li nastavit projekt po spuštění v **Průzkumník řešení**, klikněte pravým tlačítkem myši na název projektu hostitele a vyberte **nastavit jako spouštěný projekt**.
