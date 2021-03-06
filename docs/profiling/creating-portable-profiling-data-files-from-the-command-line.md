---
title: Profilace příkazového řádku – vytvoření přenosných datových souborů
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: d0584cd2a476a7552beec483dd72ad1e957800ec
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2020
ms.locfileid: "90808835"
---
# <a name="create-portable-profiling-data-files-from-the-command-line"></a>Vytváření přenosných datových souborů profilace z příkazového řádku
Aby bylo sdílení dat profilace snazší, můžete použít nástroj příkazového řádku [VSPerfReport](../profiling/vsperfreport.md) k vložení symbolů pro spuštění profilování do. soubor *VSP* .

 Můžete také vytvořit předem Analyzovaná data profilace (.* vsps*), který je menší a je rychlejší načíst v integrovaném vývojovém prostředí (IDE).

> [!NOTE]
> Ujistěte se, že symbol (.* soubory PDB*jsou k dispozici pro **VSPerfReport**. Další informace naleznete v tématu [How to: určení umístění souborů symbolů z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).
>
> Informace o cestě k **VSReport**naleznete v tématu [Určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).
>
> Data profilování v. soubor *vsps* se nedá filtrovat.

### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Chcete-li vložit symboly pro profilování, které se spustí, do dat profilace (.* VSP*) soubor

- V okně příkazového řádku zadejte následující příkaz:

   \<Path><strong>\<</strong>Soubor VSPerfReport VSP> **/PackSymbols**

   Ve výchozím nastavení je to. soubor *vsps* má název se základním názvem. soubor *VSP* . Alternativní název můžete zadat pomocí možnosti **výstup** .

### <a name="to-create-a-summary-profiling-data-file"></a>Vytvoření souhrnného datového souboru profilace

- V okně příkazového řádku zadejte následující příkaz:

   \<Path><strong>\<</strong>Soubor VSPerfReport VSP> **/SummaryFile** [**/output:** \<File Name> ]

   Ve výchozím nastavení je to. soubor *vsps* má název se základním názvem. soubor *VSP* . Alternativní název můžete zadat pomocí možnosti **výstup** .
