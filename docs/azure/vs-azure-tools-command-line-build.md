---
title: Sestavení příkazového řádku pro Azure | Microsoft Docs
description: Sestavení příkazového řádku pro Azure
author: ghogen
manager: jillfra
assetId: 94b35d0d-0d35-48b6-b48b-3641377867fd
ms.workload: azure-vs
ms.topic: how-to
ms.date: 03/05/2017
ms.author: ghogen
ms.openlocfilehash: 940636c6df2f16445b5510543b5f2a39d7076f7e
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93398940"
---
# <a name="building-azure-projects-from-the-command-line"></a>Vytváření projektů Azure z příkazového řádku
Pomocí Microsoft Build Engine (MSBuild) můžete vytvářet produkty v prostředích pro vytváření sestavení, kde není nainstalována aplikace Visual Studio. Nástroj MSBuild používá formát XML pro soubory projektu, které jsou rozšiřitelné a plně podporované Microsoftem. Pomocí formátu souboru MSBuild můžete popsat, které položky musí být sestaveny pro jednu nebo více platforem a konfigurací.

Nástroj MSBuild můžete spustit také na příkazovém řádku a toto téma popisuje tento přístup. Nastavením vlastností na příkazovém řádku můžete sestavit konkrétní konfiguraci projektu. Podobně můžete také definovat cíle, které nástroj MSBuild vytvoří. Další informace o parametrech příkazového řádku a nástroji MSBuild naleznete v tématu [msbuild Command-Line reference](../msbuild/msbuild-command-line-reference.md).

## <a name="msbuild-parameters"></a>Parametry nástroje MSBuild
Nejjednodušší způsob, jak vytvořit balíček, je spustit MSBuild s `/t:Publish` možností. Ve výchozím nastavení tento příkaz vytvoří adresář ve vztahu ke kořenové složce projektu, například `<ProjectDirectory>\bin\Configuration\app.publish\` . Při sestavování projektu Azure se generují dva soubory: samotný soubor balíčku a přiložený konfigurační soubor:

* Soubor balíčku ( `project.cspkg` )
* Konfigurační soubor ( `ServiceConfiguration.TargetProfile.cscfg` )

Ve výchozím nastavení každý projekt Azure zahrnuje jeden konfigurační soubor služby pro místní (ladicí) sestavení a druhý pro sestavení cloudu (pracovní nebo produkční). V případě potřeby však můžete přidat nebo odebrat konfigurační soubory služby. Při sestavování balíčku v sadě Visual Studio se zobrazí dotaz, který konfigurační soubor služby má být zahrnut společně s balíčkem. Když vytváříte balíček pomocí nástroje MSBuild, je ve výchozím nastavení součástí místní konfigurační soubor služby. Chcete-li zahrnout jiný konfigurační soubor služby, nastavte `TargetProfile` vlastnost příkazu MSBuild ( `MSBuild /t:Publish /p:TargetProfile=ProfileName` ).

Pokud chcete pro uložené balíčky a konfigurační soubory použít alternativní adresář, nastavte cestu pomocí `/p:PublishDir=Directory\` Možnosti, včetně koncového oddělovače zpětného lomítka.

## <a name="next-steps"></a>Další kroky
Po sestavení balíčku ho můžete nasadit do Azure.
