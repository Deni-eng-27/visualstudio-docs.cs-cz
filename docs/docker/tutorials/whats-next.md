---
title: Kurz Docker – co dál
description: Popisuje možnosti rozšíření aplikací Docker s orchestrací pomocí cloudových projektů Native Computing.
ms.date: 08/04/2020
author: nebuk89
ms.author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.topic: conceptual
ms.workload:
- azure
ms.openlocfilehash: f93185641a0814797b66eae90714e04cac83f7e5
ms.sourcegitcommit: f4d734329c82f2c8005b36af4b2b5516d90e6c63
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2020
ms.locfileid: "89039009"
---
# <a name="whats-next"></a>Kam dál

I když jste s vaším kurzem hotovi, máme ještě SPOUSTu dalších informací o kontejnerech.
Nebudete se tady podrobně, ale tady je několik dalších oblastí, které byste si měli projít.

## <a name="container-orchestration"></a>Orchestrace kontejnerů

Spouštění kontejnerů v produkčním prostředí je obtížné. Nechcete se přihlásit k počítači a stačí spustit `docker run` nebo `docker-compose up` . Proč ne? A co se stane, když se kontejnery zásobníkí? Jak můžete škálovat mezi několika počítači? Orchestrace kontejnerů tento problém vyřeší. Pomocí nástrojů, jako jsou Kubernetes, Swarm, Nomad a AKS, se tento problém vyřeší trochu různými způsoby.

Hlavním nápadem je, že máte "manažeři", kteří dostanou **očekávaný stav**. Tento stav může být "chci spustit dvě instance webové aplikace a vystavit port 80." Manažeři si pak Prohlédněte všechny počítače v clusteru a delegujete práci na uzlech Worker. Manažeři budou sledovat změny (například ukončení kontejneru) a pak pracovat, aby **skutečný stav** odpovídal očekávanému stavu.

## <a name="cloud-native-computing-foundation-projects"></a>Základní projekty Cloud Computing Native

CNCF je dodavatelově neutrální domů pro různé open-source projekty, včetně Kubernetes, Prometheus, zástupné, linkerů, zařízení NAT a dalších. Zde můžete zobrazit [odstupňované a inkubovatelné projekty zde](https://www.cncf.io/projects/) a celou [CNCF na šířku](https://landscape.cncf.io/). Existuje SPOUSTa projektů, které vám pomohou vyřešit problémy s monitorováním, protokolováním, zabezpečením, Registry imagí, zasíláním zpráv a dalšími.

Takže pokud začínáte s vývojem na šířku kontejneru a nativním vývojem aplikací v cloudu, Vítá vás! Připojte se prosím ke komunitě, položte otázky a zajistěte si učení! Rádi vám to máme!

## <a name="working-with-docker-in-vs-code"></a>Práce s Docker v VS Code

Další informace o používání rozšíření Docker VS Code:

- [Přehled rozšíření Docker VS Code](https://code.visualstudio.com/docs/containers/overview)
- [Začínáme s Node.js](https://code.visualstudio.com/docs/containers/quickstart-node)
- [Začínáme s Pythonem](https://code.visualstudio.com/docs/containers/quickstart-python)
- [Začínáme s .NET Core](https://code.visualstudio.com/docs/containers/quickstart-aspnet-core)
- [Ladění kontejnerových aplikací](https://code.visualstudio.com/docs/containers/debug-common)
