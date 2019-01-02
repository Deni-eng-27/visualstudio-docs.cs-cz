---
title: Konfigurace hostitele Docker pomocí VirtualBox | Dokumentace Microsoftu
description: Podrobné pokyny ke konfiguraci výchozí instanci Dockeru pomocí Docker Machine a VirtualBox
services: azure-container-service
documentationcenter: na
author: mlearned
manager: douge
ms.assetid: 0b1335a2-7720-42a8-8260-4e06fc00c9f6
ms.service: multiple
ms.devlang: dotnet
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: multiple
ms.date: 06/08/2016
ms.author: mlearned
ms.openlocfilehash: e332f0367119ef9b5858a66ff82947b6afb6633d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53941762"
---
# <a name="configure-a-docker-host-with-virtualbox"></a>Konfigurace hostitele Dockeru pomocí nástroje VirtualBox
## <a name="overview"></a>Přehled
Tento článek vás provede procesem konfigurace výchozí instanci Dockeru pomocí Docker Machine a VirtualBox.
Pokud používáte [Docker pro Windows](https://www.docker.com/products/docker-desktop), tato konfigurace není nutné.

## <a name="prerequisites"></a>Požadavky
Tyto nástroje je potřeba nainstalovat.

* [Panel nástrojů dockeru](https://github.com/docker/toolbox/releases)

## <a name="configuring-the-docker-client-with-windows-powershell"></a>Konfigurace klienta Dockeru pomocí Windows Powershellu
Abyste mohli nakonfigurovat klienta Dockeru, jednoduše otevřete prostředí Windows PowerShell a proveďte následující kroky:

1. Vytvoření hostitele docker výchozí instanci.

    ```PowerShell
    docker-machine create --driver virtualbox default
    ```
2. Ověřte, že výchozí instancí je konfigurována a spuštěna. (Byste měli vidět instance s názvem "default" systémem.

    ```PowerShell
    docker-machine ls
    ```

    ![docker-machine ls výstupu](media/vs-azure-tools-docker-setup/docker-machine-ls.png)
3. Nastavit výchozí jako aktuálního hostitele a nakonfigurovat vaše prostředí.

    ```PowerShell
    docker-machine env default | Invoke-Expression
    ```
4. Zobrazte aktivní kontejnery Dockeru. Seznam by měl být prázdný.

    ```PowerShell
    docker ps
    ```

    ![docker ps výstupu](media/vs-azure-tools-docker-setup/docker-ps.png)

> [!NOTE]
> Pokaždé, když restartujete vývojovém počítači, budete muset restartovat místní docker hostitele.
> Chcete-li to provést, vydejte následující příkaz z příkazového řádku: `docker-machine start default`.
