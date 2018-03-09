---
title: "Použít testovací prostředí pro devops v sadě Visual Studio | Microsoft Docs"
ms.date: 05/02/2017
ms.technology: vs-devops-test
ms.topic: article
helpviewer_keywords:
- lab environment, test lab
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b59de153b691cd67bfe70c52e62478f52795239f
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="use-a-lab-environment-for-your-devops"></a>Použít testovací prostředí pro vaše devops

Testovací prostředí je kolekce virtuálních a fyzických počítačů, které můžete použít pro vývoj a testování aplikací. Testovací prostředí může obsahovat víc rolí, které jsou potřebné k testování víceúrovňových aplikací, jako je například pracovní stanice, webové servery a servery databáze. Kromě toho můžete pracovního postupu sestavení nasazení testování s testovacím prostředí pro automatizaci procesu vytváření, nasazování a spouštění automatizovaných testů na vaší aplikace.

* **Použití testovacího plánu pro spouštění automatizovaných testů** – můžete spustit kolekce automatizovaných testů, názvem *testovacího plánu*a sledovat průběh.

* **Použití pracovního postupu sestavení nasazení testování** -pracovního postupu sestavení nasazení testování můžete použít k testování automaticky víceúrovňových aplikací. Typickým příkladem je pracovní postup, který spustí sestavení, nasadí soubory s sestavení do příslušné počítačů v testovacím prostředí a potom provede automatizovaných testů. Kromě toho můžete naplánovat pracovní postup spouštět v určitých intervalech.

* **Shromažďování diagnostických dat ze všech počítačů, i během manuálního testování** -diagnostických dat z více počítačů můžete shromažďovat současně. Například můžete během jedné testovací běh, shromažďování IntelliTrace, testovat, dopad a jiných forem dat z webového serveru, databázový server a klienta.

Zde jsou příklady topologií běžné prostředí testovacího prostředí:

| topologie | Popis |
|---|---|
|![Pouze topologie serverů](../media/topology_backend.png)| Má tohoto testovacího prostředí *topologii serveru*, což se často používá k ruční testy na serverové aplikace a který umožňuje testery zkontrolujte chyby v prostředí pomocí vlastních klientských počítačů. V topologii back-end jsou uvedeny pouze servery testovacím prostředí. Pokud použijete tento typ topologie, obvykle připojení k serverům v testovacím prostředí pomocí klientský počítač, který nejsou součástí prostředí.|
|![Cloud testovacího prostředí](../media/topology_cloud.png)| Tohoto testovacího prostředí poskytuje podobné funkce a funkce, jako _topologii serveru_, ale eliminuje požadavek pro fyzické nebo virtuální počítače spuštěné v místním prostředí; která mohou zkrátit čas instalace, zjednodušit Údržba a minimalizovat náklady. Nastavení více webů a virtuální počítače, spolu s vlastní sítě, je rychlý a snadný v cloudovém prostředí jako je Microsoft Azure.|
|![Klient server testovacího prostředí](../media/topology_clientserver.png)| Má tohoto testovacího prostředí *klient server topologie*, což se často používá k testování aplikace, která obsahuje součásti serveru a klienta. V topologii klientem a serverem všechny klientských a serverových počítačů, které slouží k testování aplikace jsou ve vašem testovacím prostředí. Při použití této topologii z každý počítač, který má dopad na testy můžete shromažďovat testovacích datech.|

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../../install/media/video-icon.png)  |    [Přehrát video,](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Managing-lab-environments-for-testing) na správu testovací prostředí pro testování. |

## <a name="use-the-cloud-with-team-services-or-team-foundation-server-build-and-release"></a>Použití cloudu s Team Services nebo Team Foundation Server sestavení a verze

Můžete provádět automatizované testování a automatizace sestavení nasazení testování pomocí [sestavení a verze](/vsts/build-release/) funkcí v Team Foundation Server (TFS) a Visual Studio Team Services. Jsou některé z výhod:

* Nepotřebujete řadič sestavení nebo testovací kontroler.
* Testovací agent byl nainstalován prostřednictvím úlohu jako součást sestavení nebo verzi.
* Je snadno přizpůsobit kroky nasazení. Již nejsou omezeny na pomocí jednoho skriptu. Můžete také využít mnoho úloh, které jsou k dispozici v rámci produktu také jako Visual Studio Marketplace.
* Nemáte k udržování testovacích sad. Testy můžete spustit přímo z binárních souborů.
* Získáte bohatší vložené reporting prostředí pro testy, které běží v každé sestavení nebo verzi.
* Můžete sledovat, které prostředky (verze, sestavení, pracovních položek, potvrzení) jsou aktuálně nasadila a otestovala na každé prostředí.
* Můžete přizpůsobit a rozšířit automatizace na snadno nasadit pro testovací prostředí s více a to i do produkčního prostředí.
* Můžete naplánovat automatizace provést vždy, když dojde k vrácení se změnami nebo potvrzení, nebo v určitý čas každý den.

Další informace najdete v tématu [použijte sestavení nebo Release management](use-build-or-rm-instead-of-lab-management.md).

## <a name="use-the-visual-studio-lab-management-features-of-microsoft-test-manager"></a>Použití funkcí Visual Studio – správa testovacího prostředí nástroje Microsoft Test Manager

Můžete vytvořit a spravovat testovací prostředí s funkcemi sady Visual Studio Lab Management nástroje Microsoft Test Manager, pokud používáte Visual Studio 2017 Enterprise edition.

Testovací agenty Lab Management automaticky instaluje na každý počítač ve vašem prostředí.

Pokud používáte Lab Management ve spojení s System Center Virtual Machine Manager (SCVMM), získáte tyto výhody při použití testovací prostředí:

* **Rychle reprodukujte konfigurace počítačů** – můžete ukládat kolekce virtuálních počítačů, které jsou nakonfigurovány k opětovnému vytvoření typické provozní prostředí. Pak můžete dělat každého testu na novou kopii uložené prostředí.

* **Reprodukujte přesný podmínky chyby** – Pokud testu, spuštění selže, můžete uložit kopii tohoto stavu testovacím prostředí a k němu přístup z výsledky sestavení nebo pracovní položku.

* **Spuštění více kopií testovacím prostředí ve stejnou dobu** -více kopií testovacím prostředí můžete spustit ve stejnou dobu bez konflikty pojmenování.

### <a name="standard-environments-and-scvmm-environments"></a>Standardní prostředí a prostředí SCVMM

Existují dva typy testovací prostředí, které můžete vytvořit pomocí sady Visual Studio Lab Management: **standardní prostředí** a **prostředí SCVMM**. Možnosti každého typu prostředí se ale liší.

**Standardní prostředí:** může obsahovat kombinaci virtuálních a fyzických počítačů. Virtuální počítače můžete také přidat na standardní prostředí, které jsou spravovány architektury virtualizace třetích stran. Kromě toho standardní prostředí nevyžadují další server prostředkům, například serveru SCVMM.

**Prostředí SCVMM:** může obsahovat pouze virtuální počítače, které jsou spravovány SCVMM (System Center Virtual Machine Manager), takže virtuální počítače v prostředí SCVMM spustit pouze v rámci virtualizace technologie Hyper-V. Prostředí SCVMM však poskytují následující funkce automatizace a správy, které nejsou k dispozici v standardní prostředích:

- **Snímků prostředí:** prostředí snímky obsahují stav testovacím prostředí, můžete rychle obnovit čisté prostředí, nebo uložit stav prostředí, která byla změněna. Můžete taky pracovního postupu sestavení nasazení testování pro automatizaci procesu ukládání a obnovení prostředí snímků.

- **Uložené prostředí:** můžete uložit kopii tohoto prostředí SCVMM a pak nasadit více kopií prostředí.

- **Izolace sítě:** izolace sítě můžete současně spustit více kopií stejné prostředí SCVMM bez název počítače je v konfliktu.

- **Šablony virtuálních počítačů:** šablonu virtuálního počítače je virtuální počítač, který má došlo jeho názvu a dalších identifikátorů odebrat. Při nasazení šablony virtuálního počítače v prostředí SCVMM nástroje Microsoft Test Manager generuje nové identifikátory. To umožňuje nasadit více kopií virtuálního počítače ve stejném prostředí nebo několika prostředí a pak spusťte virtuálních počítačů současně.

- **Uložené virtuální počítače:** virtuální počítač, který je uložený v knihovně týmového projektu a zahrnuje jedinečné identifikátory.

> [!NOTE]
> Lab Management nepodporuje SCVMM 2016.

Informace o SCVMM najdete v tématu [nástroje Virtual Machine Manager](/vsts/build-release/apps/cd/scvmm/configure-scvmm).

Standardní prostředí a prostředí SCVMM podporují řadu stejných funkcí. Existují však několik důležitých rozdílů vzít v úvahu. Následující tabulka porovnává funkce, které jsou k dispozici pro standardní prostředí a prostředí SCVMM.

|Funkce|Prostředí SCVMM|Standardní prostředí|
|----------------|------------------------|---------------------------|
|**Testování**|||
|Spouštění manuálních testů|Podporováno|Podporováno|
|Spuštění programových uživatelského rozhraní a jiné automatizované testy|Podporováno|Podporováno|
|Použití adaptérů diagnostických bohaté chyby souboru|Podporováno|Podporováno|
|**Nasazení sestavení**|||
|Automatické pracovní postupy sestavení nasazení testování|Podporováno|Podporováno|
|**Prostředí vytváření a Správa**|||
|Pomocí fyzických počítačů kromě virtuální počítače|Nepodporováno|Podporováno|
|Použijte virtuální počítače třetích stran|Nepodporováno|Podporováno|
|Automaticky nainstalujte testovacích agentů do počítačů v testovacím prostředí|Podporováno|Podporováno|
|Uložte a nasaďte stav testovacím prostředí za použití snímků prostředí|Podporováno|Nepodporováno|
|Vytvořit testovací prostředí z šablon virtuálních počítačů|Podporováno|Nepodporováno|
|Spuštění nebo zastavení nebo snímek prostředí|Podporováno|Nepodporováno|
|Připojení k prostředí pomocí prohlížeče prostředí|Podporováno|Podporováno|
|Spuštění více kopií prostředí ve stejnou dobu pomocí izolace sítě|Podporováno|Nepodporováno|

### <a name="lab-management-concepts"></a>Koncepty Lab management

Zde jsou některé další koncepty, které byste měli mít před pokračováním znají:

|Termín|Popis|
|----------|-----------------|
|Lab Center|Oblast nástroje Microsoft Test Manager kde můžete vytvořit a spravovat testovací prostředí.|
|Laboratoře týmového projektu|Kolekce testovací prostředí, které byly nastavit, aby se mohli připojit k je a spustit své virtuální počítače.|
|Knihovna týmového projektu|Archivované uložené virtuální počítače, šablony a uložené testovací prostředí, které byly naimportovány do skupiny hostitelů týmového projektu. Můžete použít položky v knihovně v prostředích SCVMM; nelze je však přidat přímo na standardní prostředí. Položky nelze spustit v knihovně; Místo toho je budete používat k nasazení nové prostředí.|
|Nasazené prostředí|Testovacím prostředí, která byla nasazena do testovacího prostředí týmového projektu, které můžete k nim připojit a spustit jeho počítače.|

Další informace o správě prostředí najdete v části:

* [Plánování testovacího prostředí](https://msdn.microsoft.com/library/ff756575%28v=vs.140%29.aspx)
* [Správa testovacího prostředí](https://msdn.microsoft.com/library/dd936084%28v=vs.140%29.aspx)
* [Nastavení pro prostředí SCVMM](https://msdn.microsoft.com/library/dd380687%28v=vs.140%29.aspx)
* [Správa oprávnění](https://msdn.microsoft.com/library/dd380760%28v=vs.140%29.aspx)
* [Nastavení změn](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx)
* [Odstraňování potíží](https://msdn.microsoft.com/library/ee853230%28v=vs.140%29.aspx)

Informace o nastavení prostředí najdete v tématu:

* [Sestavení a verze Cloudová prostředí](use-build-or-rm-instead-of-lab-management.md)
* [Standardní testovací prostředí](https://msdn.microsoft.com/library/ee390842.aspx)
* [(Virtuální) prostředí SCVMM](https://msdn.microsoft.com/library/ee943322.aspx)
* [Vytváření a používání izolovaného síťového prostředí](https://msdn.microsoft.com/library/ee518924.aspx)

## <a name="see-also"></a>Viz také

* [Instalace a konfigurace testovacích agentů](install-configure-test-agents.md)
* [Průvodce Správa testovacího prostředí sady Visual Studio](https://aka.ms/vsarsolutions)
* [Microsoft DevOps Blog](https://blogs.msdn.microsoft.com/devops/)
