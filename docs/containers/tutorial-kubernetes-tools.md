---
title: Kurz Kubernetes nástroje | Dokumentace Microsoftu
ms.date: 06/08/2018
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.workload:
- azure
ms.openlocfilehash: 5a778cac1be1ae86fbec197fa49b5d79b6ec8677
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66261194"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>Začínáme s Kubernetes nástroje sady Visual Studio

Visual Studio Kubernetes Tools zjednodušit vývoj kontejnerizovaných aplikací, které cílí na Kubernetes. Visual Studio může automaticky vytvořit konfigurace jako kódu soubory potřebné pro podporu nasazení Kubernetes, jako jsou soubory Dockerfile a Helm grafy. Ladění kódu v aktivní cluster Azure Kubernetes Service (AKS) pomocí Azure Dev mezery nebo publikovat přímo do clusteru AKS z v sadě Visual Studio.

Tento kurz se zabývá použitím sady Visual Studio, přidejte do projektu podpora pro Kubernetes a publikuje do AKS. Pokud vás zajímají hlavně pomocí [Azure Dev prostory](https://aka.ms/get-azds) pro ladění a testování projektu spuštěná ve službě AKS, můžete přejít na [Azure Dev prostory kurzu](/azure/dev-spaces/get-started-netcore-visualstudio) místo toho.

## <a name="prerequisites"></a>Požadavky

Chcete-li využívají tato nová funkce, budete potřebovat:

::: moniker range="vs-2017"
- Nejnovější verzi [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s *vývoj pro ASP.NET a web* pracovního vytížení.
- [Kubernetes tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vs-tools-for-kubernetes), která je dostupná jako samostatný soubor ke stažení.
::: moniker-end
::: moniker range="vs-2019"
- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s *vývoj pro ASP.NET a web* pracovního vytížení.
::: moniker-end
- [Docker Desktop](https://store.docker.com/editions/community/docker-ce-desktop-windows) nainstalované na pracovní stanici vývoje (to znamená, pokud spustíte Visual Studio), pokud chcete sestavit Image Dockeru, ladit místně spuštěné kontejnery Dockeru nebo publikovat ve službě AKS. (Docker je *není* vyžadované pro sestavování a ladění kontejnerů Dockeru ve službě AKS pomocí Azure Dev prostory.)
::: moniker range="vs-2017"
- Pokud chcete publikovat ze sady Visual Studio do AKS (*není* požadovaná pro ladění ve službě AKS pomocí Azure Dev mezery):

    1. [AKS nástroje pro publikování](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vs-tools-for-kubernetes), která je dostupná jako samostatný soubor ke stažení.

    1. Cluster Azure Kubernetes Service. Další informace najdete v tématu [vytváření clusteru AKS](/azure/aks/kubernetes-walkthrough-portal#create-an-aks-cluster). Nezapomeňte [připojení ke clusteru](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster) z vaší pracovní stanici.

    1. Helm CLI nainstalované na pracovní stanici vývoje. Další informace najdete v části [instalace Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md).

    1. Konfigurovat u vašeho clusteru AKS pomocí Helm `helm init` příkazu. Další informace o tom, jak to provést, najdete v části [konfigurace Helm](/azure/aks/kubernetes-helm#configure-helm).
::: moniker-end

## <a name="create-a-new-kubernetes-project"></a>Vytvořte nový projekt Kubernetes

::: moniker range="vs-2017"

Jakmile budete mít nainstalovány odpovídající nástroje, spusťte sadu Visual Studio a vytvořte nový projekt. V části **cloudu**, zvolte **aplikace typu kontejner pro Kubernetes** typ projektu. Vyberte tento typ projektu a zvolte **OK**.

![Snímek obrazovky vytváření nového projektu aplikace Kubernetes](media/tutorial-kubernetes-tools/k8s-tools-new-k8s-app.png)

::: moniker-end
::: moniker range=">= vs-2019"

V okně spuštění sady Visual Studio vyhledejte *Kubernetes*a zvolte **aplikace typu kontejner pro Kubernetes**.

![Snímek obrazovky vytváření nového projektu aplikace Kubernetes](media/tutorial-kubernetes-tools/vs-2019/k8s-tools-new-k8s-app1.png)

Zadejte název projektu.

![Snímek obrazovky vytváření nového projektu aplikace Kubernetes](media/tutorial-kubernetes-tools/vs-2019/k8s-tools-new-k8s-app2.png)

::: moniker-end

Potom můžete typu ASP.NET Core, který k vytvoření webové aplikace. Zvolte **webovou aplikaci**. Obvyklého **povolit podporu Dockeru** možnost se nezobrazí v tomto dialogovém okně.  Podporu dockeru je povoleno standardně pro aplikace typu kontejner pro Kubernetes.

::: moniker range="vs-2017"

![Snímek obrazovky výběru webové aplikace](media/tutorial-kubernetes-tools/k8s-tools-web-app-selection-screen.png)

::: moniker-end
::: moniker range=">=vs-2019"

![Snímek obrazovky výběru webové aplikace](media/tutorial-kubernetes-tools/vs-2019/k8s-tools-web-app-selection-screen-2019.png)

::: moniker-end

## <a name="add-kubernetes-support-to-an-existing-project"></a>Podpora pro Kubernetes přidat do existujícího projektu

Podpora pro Kubernetes můžete alternativně přidat do existujícího projektu webové aplikace ASP.NET Core. Chcete-li to provést, klikněte pravým tlačítkem na projekt a zvolte **přidat** > **podporu Orchestrátoru kontejnerů**.

::: moniker range="vs-2017"

![Snímek obrazovky z přidat Orchestrátor kontejnerů položky nabídky](media/tutorial-kubernetes-tools/k8s-tools-add-container-orchestrator.png)

::: moniker-end
::: moniker range=">=vs-2019"

![Snímek obrazovky z přidat Orchestrátor kontejnerů položky nabídky](media/tutorial-kubernetes-tools/vs-2019/k8s-tools-add-container-orchestrator-2019.png)

::: moniker-end

V dialogovém okně vyberte **Kubernetes a Helm** a zvolte **OK**.

![Dialogové okno snímek obrazovky z přidat Orchestrátor kontejnerů](media/tutorial-kubernetes-tools/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Sada Visual Studio vytvoří pro vás

Po vytvoření nového **aplikace typu kontejner pro Kubernetes** projektu nebo přidat podporu orchestrátoru kontejnerů Kubernetes do existujícího projektu, se zobrazí některé další soubory v projektu, které usnadňují nasazování do Kubernetes.

::: moniker range="vs-2017"

![Snímek obrazovky Průzkumníka řešení po přidání podpory Orchestrátor kontejnerů](media/tutorial-kubernetes-tools/k8s-tools-solution-explorer.png)

::: moniker-end
::: moniker range="vs-2019"

![Snímek obrazovky Průzkumníka řešení po přidání podpory Orchestrátor kontejnerů](media/tutorial-kubernetes-tools/vs-2019/k8s-tools-solution-explorer-2019.png)

::: moniker-end

Přidání souborů jsou:

- soubor Dockerfile, který vám umožní generovat Docker image kontejneru, který je hostitelem této webové aplikace. Jak uvidíte, využívá nástrojů sady Visual Studio tento soubor Dockerfile, při ladění a nasazování do Kubernetes. Pokud budete chtít pracovat přímo s image Dockeru, můžete kliknout pravým tlačítkem na soubor Dockerfile a zvolit **sestavit Image Dockeru**.

   ![Možnost snímek obrazovky z sestavit Image Dockeru](media/tutorial-kubernetes-tools/k8s-tools-build-docker-image.png)

- Helm chart a *grafy* složky. Tyto soubory yaml tvoří grafu Helm pro aplikace, které můžete použít k jejímu nasazení Kubernetes. Další informace o Helm, naleznete v tématu [ https://www.helm.sh ](https://www.helm.sh).

- *azds.yaml*. Obsahuje nastavení pro prostory vývoj Azure, který poskytuje rychlý a iterativní ladění prostředí ve službě Azure Kubernetes Service. Další informace najdete v tématu [v dokumentaci k Azure Dev prostory](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces).

::: moniker range="vs-2017"

## <a name="publish-to-azure-kubernetes-service-aks"></a>Publikování do služby Azure Kubernetes Service (AKS)

Všechny tyto soubory na místě můžete použít integrovaném vývojovém prostředí sady Visual Studio k psaní a ladění kódu aplikace stejně, jako je navíc vždy nutné. Můžete také použít [Azure Dev prostory](https://aka.ms/get-azds) rychlé spuštění a ladění kódu živě běžet v clusteru AKS. Další informace najdete [kurzu prostory vývoj Azure](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio)

Jakmile budete mít kód fungovat způsobem, který chcete, můžete publikovat přímo ze sady Visual Studio do clusteru AKS.

Chcete-li to provést, musíte nejprve zkontrolujte, že všechno, co jste nainstalovali jak je popsáno v [požadavky](#prerequisites) v rámci části položky pro publikování do AKS a projít všechny kroky příkazového řádku zadané v odkazech. Potom nastavte profil publikování, který publikuje svou image kontejneru do služby Azure Container Registry (ACR). Potom AKS o přijetí změn svou image kontejneru ze služby ACR a nasaďte je do clusteru.

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na váš *projektu* a zvolte **publikovat**.

   ![Snímek obrazovky publikovat položku nabídky](media/tutorial-kubernetes-tools/k8s-tools-publish-project.png)

2. V **publikovat** obrazovce **Container Registry** jako publikovat cílit a postupujte podle pokynů k výběru vašeho registru kontejneru. Pokud ještě nemáte registr kontejnerů, zvolte **vytvořit nový registr kontejneru Azure** si ji vytvořit v sadě Visual Studio. Další informace najdete v tématu [kterého chcete kontejner publikovat do služby Azure Container Registry](vs-azure-tools-docker-hosting-web-apps-in-docker.md).

   ![Snímek obrazovky výběru publikovat cílová obrazovka](media/tutorial-kubernetes-tools/k8s-tools-publish-to-acr.png)

3. Zpět v Průzkumníku řešení klikněte pravým tlačítkem na váš *řešení* a klikněte na tlačítko **publikování ve službě Azure AKS**.

   ![Snímek obrazovky publikovat položku nabídky Azure AKS](media/tutorial-kubernetes-tools/k8s-tools-publish-solution.png)

4. Zvolte předplatné a AKS cluster, spolu s ACR Publikovat profil, který jste právě vytvořili. Pak klikněte na tlačítko **OK**.

   ![Snímek obrazovky publikovat na obrazovku AKS](media/tutorial-kubernetes-tools/k8s-tools-publish-to-aks.png)

   Tím přejdete **publikování ve službě Azure AKS** obrazovky.

5. Zvolte **nakonfigurovat Helm** odkaz Aktualizovat příkazovým řádkem použitým k instalaci grafům helmu na serveru.

   ![Snímek obrazovky konfigurace Helm odkaz](media/tutorial-kubernetes-tools/k8s-tools-configure-helm.png)

   Aktualizace příkazového řádku je užitečné, pokud existují argumenty vlastní příkazové řádky, které chcete zadat, jako je například jiný název kontextu nebo grafu Kubernetes.

   ![Snímek obrazovky Helm konfigurovat obrazovku](media/tutorial-kubernetes-tools/k8s-tools-helm-configure-screen.png)

6. Až budete připravení nasadit, klikněte na tlačítko **publikovat** tlačítko pro publikování aplikace pro AKS.

   ![Snímek obrazovky publikovat do Azure AKS obrazovky](media/tutorial-kubernetes-tools/k8s-tools-publish-screen.png)

::: moniker-end

Blahopřejeme! Teď můžete výkon sady Visual Studio pro všechny vývoje aplikací Kubernetes.

## <a name="next-steps"></a>Další kroky

Další informace o vývoji Kubernetes v Azure najdete [dokumentaci ke službě AKS](/azure/aks).

Další informace o Azure Dev prostory načtením [dokumentace ke službě Azure Dev mezery](https://aka.ms/get-azds)
