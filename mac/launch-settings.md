---
title: Podpora launchSettings. JSON
description: Tento dokument popisuje podporu souboru launchSettings. JSON v Visual Studio pro Mac
author: sayedihashimi
ms.author: sayedha
ms.date: 09/18/2019
ms.assetid: a556f9d7-86a8-408e-aa54-392584845889
ms.openlocfilehash: 7135dd05c687e3caed3ee64618ff71c093f4cd63
ms.sourcegitcommit: 4d2620bee4688fb881e09a07ea4a264b99f0743e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322584"
---
# <a name="launchsettingsjson"></a>launchSettings. JSON

Při vývoji ASP.NET Core projektů můžete nakonfigurovat, jak má být projekt spuštěn ve scénářích vývoje, přizpůsobením obsahu souboru launchSettings. JSON. V Visual Studio pro Mac můžete tento soubor aktualizovat pomocí uživatelského rozhraní možností projektu nebo přímo úpravou. Tento soubor je stejný konfigurační soubor, který lze použít při spuštění sady Visual Studio ve Windows nebo z příkazového řádku pomocí `dotnet`. Tento soubor je uložený v projektu ve složce Properties (vlastnosti).

Podrobnější informace najdete v tématu [použití více prostředí v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/environments). V tomto článku se dozvíte, jak tento soubor aktualizovat v Visual Studio pro Mac.

## <a name="update-the-start-configuration-by-using-visual-studio-for-mac"></a>Aktualizujte počáteční konfiguraci pomocí Visual Studio pro Mac

Soubor launchSettings. JSON můžete přímo upravit v Visual Studio pro Mac, nebo můžete k jeho úpravám použít možnosti projektu. Chcete-li se dostat k možnostem projektu, klikněte pravým tlačítkem myši na projekt a vyberte **možnost možnosti**.

![Místní nabídka projektu s vybranou možností možnosti](media/vsmac-ctx-proj-options.png)

Vyberte > konfiguraceSpustit > **výchozí**.

!["Spuštění", "konfigurace" a "výchozí" v možnostech projektu](media/vsmac-run-config-default.png)

Primárně nakonfigurujete dvě věci:

 - Proměnné prostředí
 - Adresa URL aplikace pro projekt

## <a name="configure-environment-variables"></a>Konfigurace proměnných prostředí

Pomocí mřížky můžete zadat hodnoty pro proměnné prostředí. Tyto proměnné prostředí se nastaví při spuštění aplikace v Visual Studio pro Mac. Při vývoji ASP.NET Corech aplikací byste měli znát speciální `ASPNETCORE_ENVIRONMENT` proměnnou prostředí. Další informace najdete v tématu [použití více prostředí v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/environments).


## <a name="configure-the-start-url"></a>Konfigurace počáteční adresy URL

Pokud chcete nakonfigurovat adresu URL, ve které bude aplikace spuštěná, navštivte kartu **ASP.NET Core** .

![Adresa URL aplikace v možnostech projektu](media/vsmac-run-config-default-aspnetcore.png)

Tady můžete zadat adresu URL, na které bude aplikace po spuštění naslouchat.