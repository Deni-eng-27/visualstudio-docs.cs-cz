---
title: Vytvoření projektu v AI nástrojů pro Visual studio
description: Vytvoření projektu pomocí ukázkových z Galerie azure machine learning
keywords: AI, visual studio, azure machine learning
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.devlang: multiple
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- multiple
ms.openlocfilehash: 495c0d256fc6c8f36ded67166f7d12aace7a9202
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
## <a name="create-an-ai-project-from-the-azure-machine-learning-gallery-in-visual-studio"></a>Vytvoření projektu AI z Galerie Azure Machine Learning v sadě Visual Studio

Azure Machine Learning je integrován s Visual Studio Tools pro AI. Můžete ho machine learning úlohy do vzdáleného výpočetní cíle jako virtuální počítače Azure, clustery Spark a další. Další informace o [Azure Machine Learning experimentování](https://docs.microsoft.com/azure/machine-learning/preview/experimentation-service-configuration)

Jakmile jste [nainstalované Visual Studio Tools pro AI](installation.md), je snadné vytvořit nový projekt Python použití předem vytvořené recepty v galerii Azure Machine Learning ukázka.

> [!NOTE]
> Azure Machine Learning Workbench musí být nainstalován. K její instalaci prosím najdete [rychlý start Azure Machine Learning instalace](https://docs.microsoft.com/azure/machine-learning/preview/quickstart-installation)

1. Spusťte sadu Visual Studio. Otevřete **Průzkumníka serveru** otevřením **AI nástroje** nabídky a výběr **vyberte clusteru**

    ![Výběru clusteru](media\create-project-gallery\select-cluster.png)

1. Přihlaste se k předplatnému Azure Machine Learning kliknutím pravým tlačítkem myši **Azure Machine Learning** vyberte uzel v Průzkumníku serveru **přihlášení** a postupujte podle pokynů.

    ![přihlášení](media\create-project-gallery\azureml-login.png)

2. Vyberte **AI nástroje > Azure Machine Learning ukázka Galerie**.

    ![Ukázka Galerie](media\create-project-gallery\gallery.png)

1. Tento rychlý start, vyberte "**MNIST pomocí TensorFlow**" ukázkové a klikněte na tlačítko **nainstalovat**. Přináší tyto výhody:

 - **Skupina prostředků**: Skupina prostředků Azure, kde bude uložena metadata
 - **Účet**: experimenty Azure Machine Learning účtu
 - **Pracovní prostor**: pracovní prostor Azure Machine Learning
 - **Typ projektu**: rozhraní machine learning. V takovém případě zvolte **TensorFlow**
 - **Přidat do řešení**: Určuje, zda chcete přidat do vašeho aktuálního řešení Visual Studio nebo vytvoření a otevřete nový řešení
 - **Cesta k projektu**: umístění pro uložení kód
 - **Název projektu**: typ **TensorFlowMNIST**

![Výsledný projektu při použití šablony aplikace Python](media/create-project-gallery/new-AzureSampleProject.png)

1. Visual Studio vytvoří soubor projektu ( `.pyproj` soubor na disku) společně s další soubory definované v ukázce. Projekt se šablonou "MNIST" obsahuje několik souborů.

    ![mnist](media\create-project-gallery\azml-mnist.png)

1. Odeslání úlohy do Azure Machine Learning.

    ![mnist](media\create-project-gallery\submit-azml.png)

1. Spusťte kontejner Docker nebo na místním počítači

    ![mnist](media\create-project-gallery\azml-local.png)