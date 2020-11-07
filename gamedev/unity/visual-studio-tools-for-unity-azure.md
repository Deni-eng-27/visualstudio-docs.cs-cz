---
title: Programování pomocí Visual Studio Tools for Unity a Azure | Microsoft Docs
description: Program s Visual Studio Tools for Unity a Azure. Azure poskytuje škálovatelné řešení pro ukládání telemetrie a dalších herních dat v cloudu.
ms.custom: ''
ms.date: 12/18/2017
ms.reviewer: crdun
ms.technology: vs-unity-tools
ms.prod: visual-studio-dev16
ms.topic: conceptual
ms.assetid: 7921D4C7-5526-42F5-8E03-82D3E33A893F
author: therealjohn
ms.author: johmil
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 30494283fd652a1f3c5ca9a12d68982714a73309
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "94341583"
---
# <a name="program-with-unity-and-azure"></a>Programování v Unity s Azure

Azure poskytuje škálovatelné řešení pro ukládání telemetrie a dalších herních dat v cloudu. S vydáním Unity 2017 služba experimentální podpory pro .NET 4,6 zjednodušuje integraci Azure, a to díky tomu, že umožňuje používat sady SDK Azure .NET.

## <a name="experimental-azure-sdks"></a>Experimentální sady Azure SDK

> [!NOTE]
> Tyto sady SDK nejsou podporované, ale poskytují zákazníkům pomoc při pokusu o experimentální podporu .NET 4,6 Unity.

Přejděte [do izolovaného prostoru (sandbox)](/sandbox/) a vyzkoušejte následující experimentální sady Azure SDK s Unity:

* [Azure Storage SDK pro Unity](/sandbox/gamedev/unity/azure-storage-unity?wt.mc_id=azgamedev-sandbox-brpeek)
* [Azure Event Hubs SDK pro Unity](/sandbox/gamedev/unity/azure-event-hubs-unity?WT.mc_id=azgamedev-sandbox-brpeek)
* [Azure Mobile Apps SDK pro Unity](/sandbox/gamedev/unity/azure-mobile-apps-unity?WT.mc_id=azgamedev-sandbox-brpeek)

## <a name="azure-sdk-sample"></a>Ukázka sady Azure SDK

K dispozici je také [Jednoduchá ukázková hra](/sandbox/gamedev/unity/samples/azure-mobile-apps-unity-racer) , která využívá sadu Azure Easy Tables SDK a Unity. Hra používá úložiště dat Azure Easy Table ke sledování vysokého skóre tabulek výsledků a uložení telemetrie v herním zařízení a je k dispozici ke [stažení z GitHubu](https://github.com/BrianPeek/AzureSamples-Unity).

![Ukázka snímku hry](media/vs/vstu-azure-test-sample-game-image2.png)
