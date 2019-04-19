---
title: Řešení potíží s chybami klienta Docker ve Windows | Dokumentace Microsoftu
description: Řešení problémů, které zaznamenáte při používání sady Visual Studio k vytvoření a nasazení webové aplikace do Docker ve Windows pomocí sady Visual Studio.
ms.technology: vs-azure
author: ghogen
manager: jillfra
ms.custom: seodec18
ms.assetid: 346f70b9-7b52-4688-a8e8-8f53869618d3
ms.devlang: dotnet
ms.topic: conceptual
ms.workload: multiple
ms.date: 10/13/2017
ms.author: ghogen
ms.openlocfilehash: dd27ff29d8e0d7581046d18457877532d4ce4c56
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537943"
---
# <a name="troubleshoot-visual-studio-development-with-docker"></a>Řešení potíží při vývoji v sadě Visual Studio pomocí Dockeru

Při práci s nástroje kontejneru sady Visual Studio, může dojít k potížím při sestavování nebo ladění aplikace. Níže jsou některé běžné kroků pro řešení potíží.

## <a name="volume-sharing-is-not-enabled-enable-volume-sharing-in-the-docker-ce-for-windows-settings--linux-containers-only"></a>Sdílení svazků není povolené. Povolte sdílení svazků v nastavení Dockeru CE pro Windows (pouze pro kontejnery Linuxu)

K vyřešení tohoto problému:

1. Klikněte pravým tlačítkem na **Docker pro Windows** v oznamovací oblasti a pak vyberte **nastavení**.
1. Vyberte **sdílené jednotky** a sdílené složky systémové jednotce spolu s na jednotku, ve které se nachází projektu.

> [!NOTE]
> Pokud se zdá, že sdílené soubory, můžete stále chcete-li znovu povolit sdílení svazků, klikněte na odkaz "Resetovat přihlašovací údaje …" v dolní části dialogového okna. Chcete-li pokračovat po resetování přihlašovacích údajů, budete muset restartovat Visual Studio.

![sdílené jednotky](media/troubleshooting-docker-errors/shareddrives.png)

> [!TIP]
> Později než Visual Studio 2017 verze 15.6 výzvu verzí sady Visual Studio, kdy **sdílené jednotky** nejsou nakonfigurované.

### <a name="container-type"></a>Typ kontejneru

Při přidávání podpory Docker do projektu, zvolte Windows nebo Linuxem kontejneru. Hostitele Docker musí běžet stejný typ kontejneru. Chcete-li změnit typ kontejneru v běžící instanci Dockeru, klikněte pravým tlačítkem na ikonu Dockeru na hlavním panelu a vyberte **přepnout na kontejnery Windows...**  nebo **přepnout na kontejnery Linuxu...** .

## <a name="unable-to-start-debugging"></a>Nelze spustit ladění

Jedním z důvodů může souviset s tím, že komponenty zastaralé ladění ve složce profilu uživatele. Spusťte následující příkazy k odebrání těchto složek tak, aby se stáhnou nejnovější ladění komponenty na příští relaci ladění.

- del %userprofile%\vsdbg
- del %userprofile%\onecoremsvsmon

## <a name="errors-specific-to-networking-when-debugging-your-application"></a>Chyby specifické pro sítě při ladění aplikace

Pokuste se spustit skript ke stažení z [sítě hostitele kontejneru vyčištění](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-server-container-tools/CleanupContainerHostNetworking), která obnoví komponenty související se sítí na hostitelském počítači.

## <a name="mounts-denied"></a>Připojení byl odepřen

Při použití Dockeru pro macOS, pravděpodobně dojde k chybě odkazující na složku /usr/local/share/dotnet/sdk/NuGetFallbackFolder. Přidat složku na kartě Sdílení souborů v Dockeru

## <a name="microsoftdockertools-github-repo"></a>Úložiště GitHub Microsoft/DockerTools

V případě jiných problémů dojde, naleznete v tématu [Microsoft/DockerTools](https://github.com/microsoft/dockertools/issues) problémy.