---
title: Použití testovacího prostředí pro DevOps
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- lab environment, test lab
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: d33562c686365029bc75781c76ad26d772dfcf66
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72653088"
---
# <a name="use-a-lab-environment-for-your-devops"></a>Použití testovacího prostředí pro DevOps

Testovací prostředí je kolekce virtuálních a fyzických počítačů, které můžete použít k vývoji a testování aplikací. Testovací prostředí může obsahovat více rolí potřebných k testování vícevrstvých aplikací, jako jsou pracovní stanice, webové servery a databázové servery. Kromě toho můžete použít pracovní postup sestavení-nasazení-testování s testovacím prostředím pro automatizaci procesu sestavování, nasazování a spouštění automatizovaných testů ve vaší aplikaci.

* **Použití testovacího plánu pro spuštění automatizovaných testů** – můžete spustit kolekci automatizovaných testů, tzv. *plán testování*, a zobrazit průběh.

* **Použijte pracovní postup sestavení-nasazení-testování** – pracovní postup sestavení-nasazení-testování můžete použít k automatickému testování vícevrstvých aplikací. Typickým příkladem je pracovní postup, který spustí sestavení, nasadí soubory sestavení do příslušných počítačů v testovacím prostředí a provede automatizované testy. Kromě toho můžete naplánovat spuštění pracovního postupu v určitých intervalech.

* **Shromažďovat diagnostická data ze všech počítačů, a to i během manuálního testování** – můžete shromažďovat diagnostická data z více počítačů současně. Například během jednoho testovacího běhu můžete shromažďovat IntelliTrace, dopad testu a další formy dat z webového serveru, databázového serveru a klienta.

Tady jsou příklady běžných topologií testovacího prostředí:

| Topologií | Popis |
|---|---|
|![Topologie pouze serveru](../media/topology_backend.png)| Toto testovací prostředí má *topologii serveru*, která se často používá ke spouštění manuálních testů u serverových aplikací a který umožňuje testerům používat vlastní klientské počítače k ověření chyb v prostředí. V back-endu topologie obsahuje testovací prostředí pouze servery. Když použijete tento typ topologie, obvykle se k serverům v testovacím prostředí připojíte pomocí klientského počítače, který není součástí prostředí.|
|![Cloudové testovací prostředí](../media/topology_cloud.png)| Toto testovací prostředí poskytuje podobné možnosti a funkce jako _topologie serveru_, ale odebírá požadavek fyzických nebo virtuálních počítačů spuštěných v místním prostředí. což může zkrátit dobu nastavení, zjednodušit údržbu a minimalizovat náklady. Nastavení více webů a virtuálních počítačů společně s vlastními sítěmi je rychlé a snadné v cloudovém prostředí, jako je Microsoft Azure.|
|![Testovací prostředí klienta a serveru](../media/topology_clientserver.png)| V tomto testovacím prostředí je *topologie typu klient-server*, která se často používá k otestování aplikace, která má součásti serveru a klienta. V topologii klienta/serveru jsou všechny počítače klienta a serveru, které se používají k testování vaší aplikace, ve vašem testovacím prostředí. Při použití této topologie můžete shromažďovat testovací data z každého počítače, který má vliv na testy.|

| | |
|---|---|
| ![ikona filmové kamery pro video](../../install/media/video-icon.png) | [Podívejte se na video](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Managing-lab-environments-for-testing) o správě testovacích prostředí pro testování. |

## <a name="use-the-cloud-with-azure-pipelines-or-team-foundation-server-build-and-release"></a>Použití cloudu s Azure Pipelines nebo Team Foundation Server sestavení a vydání

Automatizované testování a automatizaci Build-Deploy-test můžete provádět pomocí funkcí [sestavení a vydání](/azure/devops/pipelines/index?view=vsts) v Team Foundation Server (TFS) a Azure test Plans. Mezi výhody patří:

* Nepotřebujete kontrolér sestavení nebo řadič testu.
* Testovací agent je nainstalován prostřednictvím úlohy jako součást sestavení nebo vydání.
* Postup nasazení lze snadno přizpůsobit. Nebudete už mít přístup k použití jednoho skriptu. Můžete také využít celou řadu úloh, které jsou k dispozici v produktu, a také v Visual Studio Marketplace.
* Nemusíte spravovat testovací sady. Můžete přímo spouštět testy z binárních souborů.
* Získáte rozsáhlejší prostředí pro vytváření sestav pro testy, které jsou spuštěny v rámci každého sestavení nebo vydání.
* Můžete sledovat, které prostředky (verze, sestavení, pracovní položky, potvrzení) jsou aktuálně nasazeny a testovány v každém prostředí.
* Automatizaci můžete přizpůsobit a rozšíříte tak, aby bylo možné snadno nasadit do více testovacích prostředí a dokonce i do produkčního prostředí.
* Automatizaci můžete naplánovat tak, že dojde k vrácení se změnami nebo potvrzení nebo v konkrétní době každý den.

Další informace najdete v tématu [použití nástroje Build nebo Release Management](use-build-or-rm-instead-of-lab-management.md).

## <a name="use-the-visual-studio-lab-management-features-of-microsoft-test-manager"></a>Použití funkcí Visual Studio Lab Management Microsoft Test Manager

Při použití Visual Studio Enterprise Edition můžete vytvářet a spravovat testovací prostředí s funkcemi Visual Studio Lab Management Microsoft Test Manager.

Lab Management automaticky nainstaluje testovací agenty na všechny počítače ve vašem prostředí.

Pokud používáte Lab Management ve spojení s System Center Virtual Machine Manager (SCVMM), získáte také tyto výhody při použití testovacích prostředí:

* **Rychlé reprodukci konfigurací počítačů** – můžete ukládat kolekce virtuálních počítačů, které jsou nakonfigurované tak, aby znovu vytvořily typická produkční prostředí. Pak můžete každý testovací běh provést na nové kopii uloženého prostředí.

* **Reprodukování přesné podmínky chyby** – Pokud se testovací běh nezdařil, můžete uložit kopii stavu testovacího prostředí a přistupovat k němu z výsledků sestavení nebo pracovní položky.

* **Spustit více kopií testovacího prostředí současně** – můžete spouštět více kopií testovacího prostředí současně bez konfliktů názvů.

### <a name="standard-environments-and-scvmm-environments"></a>Standardní prostředí a prostředí SCVMM

Existují dva typy testovacích prostředí, které můžete vytvořit pomocí Visual Studio Lab Management: **standardní prostředí** a **prostředí SCVMM**. Funkce každého typu prostředí se ale liší.

**Standardní prostředí:** můžou obsahovat kombinaci virtuálních a fyzických počítačů. Virtuální počítače můžete také přidat do standardního prostředí, které jsou spravovány virtualizačními platformami třetích stran. Standardní prostředí navíc nevyžadují další prostředky serveru, jako je například server SCVMM.

**Prostředí SCVMM:** mohou obsahovat pouze virtuální počítače, které jsou spravovány nástrojem scvmm (System Center Virtual Machine Manager), takže virtuální počítače v prostředích SCVMM lze spustit pouze v architektuře virtualizace technologie Hyper-V. Prostředí SCVMM však poskytují následující funkce pro automatizaci a správu, které nejsou k dispozici ve standardních prostředích:

- **Snímky prostředí:** Snímky prostředí obsahují stav testovacího prostředí, takže můžete rychle obnovit čisté prostředí nebo uložit stav prostředí, které bylo upraveno. Můžete také použít pracovní postup sestavení-nasazení-testování pro automatizaci procesu ukládání a obnovování snímků prostředí.

- **Uložená prostředí:** Můžete uložit kopii prostředí SCVMM a potom nasadit více kopií tohoto prostředí.

- **Izolace sítě:** Izolace sítě umožňuje souběžně spouštět více identických kopií prostředí SCVMM bez konfliktů názvů počítačů.

- **Šablony virtuálních počítačů:** Šablona virtuálního počítače je virtuální počítač, který má svůj název a odebrané jiné identifikátory. Když je šablona virtuálního počítače nasazená v prostředí SCVMM, Microsoft Test Manager generuje nové identifikátory. To umožňuje nasadit více kopií virtuálního počítače ve stejném prostředí nebo ve více prostředích a pak virtuální počítače spustit současně.

- **Uložené Virtual Machines:** Virtuální počítač, který je uložen v knihovně projektu a obsahuje jedinečné identifikátory.

> [!NOTE]
> Lab Management nepodporuje SCVMM 2016.

Informace o SCVMM najdete v tématu [Virtual Machine Manager](/azure/devops/pipelines/?view=vsts).

Standardní prostředí a prostředí SCVMM podporují mnoho stejných funkcí. Je ale potřeba vzít v úvahu několik důležitých rozdílů. Následující tabulka porovnává funkce, které jsou k dispozici pro standardní prostředí a prostředí SCVMM.

|Funkce|Prostředí SCVMM|Standardní prostředí|
|-|------------------------|-|
|**Testování**|||
|Spuštění manuálních testů|Podporováno|Podporováno|
|Spuštění kódovaného uživatelského rozhraní a dalších automatizovaných testů|Podporováno|Podporováno|
|Soubor s bohatou chybou pomocí diagnostických adaptérů|Podporováno|Podporováno|
|**Nasazení buildu**|||
|Automatické pracovní postupy sestavení-nasazení-testování|Podporováno|Podporováno|
|**Vytváření a Správa prostředí**|||
|Použití fyzických počítačů kromě virtuálních počítačů|Není podporováno|Podporováno|
|Použití virtuálních počítačů třetích stran|Není podporováno|Podporováno|
|Automaticky instalovat testovací agenty do počítačů v testovacím prostředí|Podporováno|Podporováno|
|Uložení a nasazení stavu testovacího prostředí pomocí snímků prostředí|Podporováno|Není podporováno|
|Vytváření testovacích prostředí z šablon virtuálních počítačů|Podporováno|Není podporováno|
|Prostředí pro spuštění/zastavení/snímek|Podporováno|Není podporováno|
|Připojení k prostředí pomocí prohlížeče prostředí|Podporováno|Podporováno|
|Spuštění více kopií prostředí současně pomocí izolace sítě|Podporováno|Není podporováno|

### <a name="lab-management-concepts"></a>Koncepty správy testovacího prostředí

Tady je několik dalších konceptů, které byste před pokračováním měli znát:

|Termín|Popis|
|-|-----------------|
|Centrum testovacích prostředí|Oblast Microsoft Test Manager, kde můžete vytvářet a spravovat testovací prostředí.|
|Testovací prostředí projektu Azure DevOps|Kolekce laboratorních prostředí, která byla nastavena, abyste se k nim mohli připojit a spouštět jejich virtuální počítače.|
|Knihovna projektů Azure DevOps|Archiv uložených virtuálních počítačů, šablon a uložených laboratorních prostředí, které byly importovány do skupiny hostitelů projektu. Položky v knihovně můžete použít v prostředích SCVMM. nemůžete je ale přidat přímo do standardního prostředí. Položky v knihovně nemůžete spustit. místo toho je použijete k nasazení nového prostředí.|
|Nasazené prostředí|Testovací prostředí, které bylo nasazeno do testovacího prostředí projektu, abyste se k němu mohli připojit a spustit jeho počítače.|

Další informace o správě testovacího prostředí najdete v těchto tématech:

* [Plánování testovacího prostředí](https://msdn.microsoft.com/library/ff756575%28v=vs.140%29.aspx)
* [Správa testovacího prostředí](https://msdn.microsoft.com/library/dd936084%28v=vs.140%29.aspx)
* [Nastavení pro prostředí SCVMM](https://msdn.microsoft.com/library/dd380687%28v=vs.140%29.aspx)
* [Spravovat oprávnění](https://msdn.microsoft.com/library/dd380760%28v=vs.140%29.aspx)
* [Změnit nastavení](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx)
* [Odstraňování potíží](https://msdn.microsoft.com/library/ee853230%28v=vs.140%29.aspx)

Informace o nastavení prostředí najdete v těchto tématech:

* [Sestavování a vydávání cloudových prostředí](use-build-or-rm-instead-of-lab-management.md)
* [Standardní testovací prostředí](https://msdn.microsoft.com/library/ee390842.aspx)
* [SCVMM (virtuální) prostředí](https://msdn.microsoft.com/library/ee943322.aspx)
* [Vytvoření a použití izolovaného prostředí sítě](https://msdn.microsoft.com/library/ee518924.aspx)

## <a name="see-also"></a>Viz také:

* [Instalace a konfigurace testovacích agentů](../../test/lab-management/install-configure-test-agents.md)
* [Průvodce Visual Studio Lab Management](https://aka.ms/vsarsolutions)
* [Blog k Microsoft DevOps](https://devblogs.microsoft.com/devops/)
