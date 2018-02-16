---
title: "Odstranění autorizace proxy server vyžaduje chyby | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e33e0e2896ccb3a5f7fe6d6da57f509af30d77fe
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2018
---
# <a name="proxy-authorization-required"></a>Povolení proxy požadovaného

Této chybě obvykle dochází, když jsou uživatelé připojeni k Internetu prostřednictvím proxy serveru a proxy server blokuje volání, které provádí některým síťovým prostředkům v sadě Visual Studio.

## <a name="to-correct-this-error"></a>Oprava této chyby

- Restartujte sadu Visual Studio. By se zobrazit dialogové okno ověřování proxy serveru. V dialogovém okně zadejte přihlašovací údaje.

- Pokud předchozí krok problém nevyřeší, to může být způsobeno proxy serveru nezobrazí výzvu k zadání pověření pro http://go.microsoft.com adresy, ale nebude tak *. visualStudio.com adresy. Pro tyto servery musíte do seznamu povolených IP adres v následujícím seznamu adres URL pro odblokování všech scénářích přihlášení v sadě Visual Studio:

    - *.windows.net

    - *.microsoftonline.com

    - *.visualstudio.com

    - *.microsoft.com

    - *.live.com

- V opačném případě můžete odebrat adresu http://go.microsoft.com ze seznamu povolených serverů tak, aby proxy ověřovací dialog zobrazí pro adresu http://go.microsoft.com a koncové body serveru při restartu sady Visual Studio.

    NEBO

- Pokud chcete k použití výchozích pověření s proxy, můžete provést následující:

    1. Najít **devenv.exe.config** (konfigurační soubor devenv.exe) v: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** nebo **% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**.

    1. V konfiguračním souboru najít `<system.net>` blokovat a přidejte tento kód:

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        Je třeba vložit správné proxy adres pro vaši síť v `proxyaddress="<http://<yourproxy:port#>`.

    NEBO

- Můžete také podle pokynů v [tento příspěvek](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) přidat kód, který vám umožní použít proxy server.
