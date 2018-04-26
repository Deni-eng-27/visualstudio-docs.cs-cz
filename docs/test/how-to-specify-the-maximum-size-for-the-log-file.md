---
title: Velikost souboru protokolu pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging
ms.assetid: 417059bf-37ae-4e7a-b9b0-29bd71f1414f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7faf5402f495eefe64000c67048bcb85c9197388
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-the-maximum-size-for-the-log-file-for-load-tests"></a>Postupy: určení maximální velikosti souboru protokolu pro zátěžové testy

Ve výchozím nastavení je maximální velikost souboru protokolu, který se používá pro zátěžové testy hodnotu 20 megabajtů. Tuto hodnotu můžete změnit úpravou konfiguračního souboru, který je přidružený k službě řadiče.

## <a name="specify-the-maximum-log-file-size-for-load-test"></a>Zadejte maximální velikosti souboru pro zátěžový Test

1.  Otevřete *QTCcontroller.exe.config* nachází v % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config konfigurační soubor XML.

2.  Vyhledejte `<add key="LogSizeLimitInMegs" value="20"/>` položky v rámci `<appSettings>` značky.

    ```xml
    <appSettings>
        <add key="LogSizeLimitInMegs" value="20"/>
        <add key="AgentConnectionTimeoutInSeconds" value="120"/>
        <add key="AgentSyncTimeoutInSeconds" value="300"/>
        <add key="ControllerServicePort" value="6901"/>
        <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
        <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
        <add key="CreateTraceListener" value="no"/>
      </appSettings>
    ```

3.  Upravit `value ="20"` na maximální povolenou velikost chcete určit soubor protokolu.

    > [!NOTE]
    > Zadáním hodnoty 0, určuje, že soubor protokolu omezenou velikost podle volného místa na disku.

## <a name="see-also"></a>Viz také

- [Úprava nastavení protokolování zátěžových testů](../test/modify-load-test-logging-settings.md)
- [Konfigurace portů pro testovací Kontroléry a testovací agenty](../test/configure-ports-for-test-controllers-and-test-agents.md)