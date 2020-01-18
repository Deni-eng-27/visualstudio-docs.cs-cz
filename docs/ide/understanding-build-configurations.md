---
title: Vysvětlení konfigurací sestavení
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
f1_keywords:
- SolutionProperties.ActiveConfig
- vs.build.newprojectconfiguration
- vc.proj.configurationsctrl.multipleconfigs
- vs.build.editsolutionconfigurations
- vs.build.editprojectconfigurations
- vs.multipleconfigurations
- vs.build.newsolutionconfiguration
- VS.ConfigurationManager
- VS.MultipleConfig
helpviewer_keywords:
- solution build configurations, about build configurations
- build configurations
- project build configurations
- build configurations, advanced
- projects [Visual Studio], build configuration
- solutions [Visual Studio], build configuration
ms.assetid: 934c727d-3a22-429c-bd13-3552cecf2e24
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47a76c054a71d88800bf1af225c332c9df3d2035
ms.sourcegitcommit: e3c3d2b185b689c5e32ab4e595abc1ac60b6b9a8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/18/2020
ms.locfileid: "76269156"
---
# <a name="understand-build-configurations"></a>Vysvětlení konfigurací sestavení

Konfigurace sestavení potřebujete, pokud potřebujete sestavit projekty s jiným nastavením. Například **ladění** a **vydání** jsou konfigurace a při jejich sestavování se používají různé možnosti kompilátoru.  Jedna konfigurace je aktivní a je uvedena na panelu příkazů v horní části rozhraní IDE.

![Aktivní konfigurace](media/understanding-build-configurations/active-config.png)

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac najdete v tématu [konfigurace sestavení v Visual Studio pro Mac](/visualstudio/mac/configurations).

Konfigurace a řízení platformy, kde jsou uloženy vytvořené výstupní soubory. V případě, že Visual Studio sestaví projekt, výstup se umístí do podsložky projektu s názvem aktivní konfigurace (například *bin/ladit/x86*), ale můžete ho změnit.

Vlastní konfigurace sestavení můžete vytvořit na úrovni řešení a projektu. Konfigurace řešení určuje, které projekty jsou zahrnuty v sestavení, pokud je tato konfigurace aktivní. Budou sestaveny pouze projekty, které jsou zadány v aktivní konfiguraci řešení. Konfigurace projektu určuje, které nastavení sestavení a možnosti kompilátoru se použijí při sestavování projektu.

Chcete-li vytvořit, vybrat, upravit nebo odstranit konfiguraci, můžete použít **Configuration Manager**. Chcete-li jej otevřít, v panelu nabídek vyberte možnost **sestavit** > **Configuration Manager**nebo do vyhledávacího pole zadejte pouze **konfiguraci** . Můžete také použít seznam **Konfigurace řešení** na panelu nástrojů **standardní** k výběru konfigurace nebo otevření **Configuration Manager**.

![Správce konfigurace](media/understanding-build-configurations/config-manager.png)

> [!NOTE]
> Pokud nemůžete najít nastavení konfigurace řešení na panelu nástrojů a nemůžete získat přístup k **Configuration Manager**, může být použito nastavení pro vývoj [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Další informace najdete v tématu [Postupy: Správa konfigurací pomocí Visual Basic nastavení pro vývojáře](../ide/how-to-manage-build-configurations-with-visual-basic-developer-settings-applied.md).

Ve výchozím nastavení jsou konfigurace **ladění** a **vydání** zahrnuty v projektech, které jsou vytvořeny pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablon. Konfigurace **ladění** podporuje ladění aplikace **a konfigurace vydaných** verzí vytvoří verzi aplikace, kterou lze nasadit. Další informace najdete v tématu [Postupy: nastavení ladění a konfigurací vydání](../debugger/how-to-set-debug-and-release-configurations.md). Můžete také vytvořit vlastní konfigurace řešení a konfigurace projektu. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md).

## <a name="solution-configurations"></a>Konfigurace řešení

Konfigurace řešení určuje, jak mají být projekty v řešení sestaveny a nasazeny. Chcete-li upravit konfiguraci řešení nebo definovat nový, v **Configuration Manager**v části **Konfigurace aktivního řešení**vyberte možnost **Upravit** nebo **Nový**.

Každá položka v poli **kontexty projektu** v konfiguraci řešení představuje projekt v řešení. Pro každou kombinaci **aktivní konfigurace řešení** a **platformy aktivního řešení**můžete nastavit, jak se má každý projekt používat. (Další informace o platformách řešení najdete v tématu [porozumění platformám sestavení](../ide/understanding-build-platforms.md).)

Při definování nové konfigurace řešení a zaškrtnutí políčka **vytvořit nové konfigurace projektu** [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky přiřadí novou konfiguraci všem projektům. Podobně, při definování nové platformy řešení a zaškrtnutí políčka **vytvořit nové projektové platformy** [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky přiřadí novou platformu všem projektům. Také Pokud přidáte projekt, který cílí na novou platformu, Visual Studio přidá tuto platformu do seznamu platforem řešení a přiřadí je ke všem projektům. Můžete přesto upravit nastavení pro každý projekt.

Aktivní konfigurace řešení také poskytuje kontext rozhraní IDE. Například pokud pracujete na projektu a konfigurace určuje, že bude sestavena pro mobilní zařízení, zobrazí **Sada nástrojů** pouze položky, které lze použít v projektu mobilního zařízení.

## <a name="project-configurations"></a>Konfigurace projektu

Konfigurace a platforma, které cílí na projekt, se používají společně k určení nastavení sestavení a možností kompilátoru, které se použijí při sestavení. Projekt může mít různá nastavení pro každou kombinaci konfigurace a platformy. Chcete-li upravit vlastnosti projektu, otevřete místní nabídku projektu v **Průzkumník řešení**a zvolte možnost **vlastnosti**.  V horní části karty **sestavení** Návrháře projektu vyberte aktivní konfiguraci pro úpravu jeho nastavení sestavení.

![Konfigurace Návrháře projektu](media/understanding-build-configurations/project-designer-configuration.png)

## <a name="how-visual-studio-assigns-project-configurations"></a>Jak Visual Studio přiřadí konfigurace projektu

Pokud definujete novou konfiguraci řešení a nekopírujete nastavení z existujícího projektu, Visual Studio použije následující kritéria k přiřazení výchozích konfigurací projektu. Kritéria jsou vyhodnocována v uvedeném pořadí.

1. Pokud má projekt název konfigurace ( *\<název konfigurace > \<název platformy >* ), který přesně odpovídá názvu nové konfigurace řešení, tato konfigurace je přiřazena. V názvech konfigurace se nerozlišují velká a malá písmena.

1. Pokud má projekt název konfigurace, ve kterém část konfigurace-název odpovídá nové konfiguraci řešení, je tato konfigurace přiřazena, ať už část platformy odpovídá nebo ne.

1. Pokud se stále neshoduje, první konfigurace, která je uvedená v projektu, je přiřazena.

## <a name="how-visual-studio-assigns-solution-configurations"></a>Jak Visual Studio přiřadí konfigurace řešení

Při vytváření konfigurace projektu (v **Configuration Manager**kliknutím na možnost **Nový** v rozevírací nabídce ve sloupci **Konfigurace** tohoto projektu) a zaškrtnutím políčka **vytvořit nové konfigurace řešení** vyhledá aplikace Visual Studio konfiguraci řešení se stejným názvem a sestaví projekt na všech podporovaných platformách. V některých případech aplikace Visual Studio přejmenuje existující konfigurace řešení nebo definuje nové.

Visual Studio používá následující kritéria k přiřazení konfigurací řešení.

- Pokud konfigurace projektu nespecifikuje platformu nebo určuje jenom jednu platformu, pak se v konfiguraci řešení, jejíž název shoduje s názvem nové konfigurace projektu, najde nebo přidá. Výchozí název této konfigurace řešení nezahrnuje název platformy; má formu *\<název konfigurace projektu >* .

- Pokud projekt podporuje více platforem, je konfigurace řešení buď nalezena, nebo přidána pro každou podporovanou platformu. Název každé konfigurace řešení zahrnuje název konfigurace projektu i název platformy a má formu *\<název konfigurace projektu > \<název platformy >* .

## <a name="see-also"></a>Viz také:

- [Návod: Sestavení aplikace](../ide/walkthrough-building-an-application.md)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
- [Řešení a projekty](../ide/solutions-and-projects-in-visual-studio.md)
- [Reference CC++ /Build](/cpp/build/reference/c-cpp-building-reference)
- [Porozumění platformám sestavení](understanding-build-platforms.md)
- [Konfigurace sestavení (Visual Studio pro Mac)](/visualstudio/mac/configurations)
