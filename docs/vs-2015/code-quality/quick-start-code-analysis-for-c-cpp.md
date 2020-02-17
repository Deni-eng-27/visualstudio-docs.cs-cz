---
title: 'Rychlé zprovoznění: Analýza kódu pro C-C++ | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
ms.assetid: 6110b8ba-0af6-4acd-b1ba-bb0551f90e44
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: e9db06ec0748ce4499afb423fac03886cd763301
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2020
ms.locfileid: "77278478"
---
# <a name="quick-start-code-analysis-for-cc"></a>Rychlé zahájení: Analýza kódu pro C/C++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kvalitu aplikace můžete zlepšit spuštěním analýzy kódu pravidelně na jazyku C nebo C++ kódu. To vám může pomáhat najít běžné problémy, porušení dobrého programovacího postupu nebo vady, které se obtížně zjišťují prostřednictvím testování. Upozornění analýzy kódu se liší od kompilátoru chyby a upozornění, protože analýza kódu hledá vzory v konkrétním kódu, které jsou platné, ale přesto vytvořit problémy pro vy nebo ostatní uživatelé, kteří používají váš kód.  
  
## <a name="in-this-topic"></a>V tomto tématu  
  
- [Konfigurace sad pravidel pro projekt](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_ConfigureRuleSets)  
  
- [Spustit analýzu kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Run)  
  
- [Analyzovat a vyřešit upozornění analýzy kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Analyze)  
  
- [Potlačení upozornění analýzy kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Suppress)  
  
- [Vytváření pracovních položek pro upozornění analýzy kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Creating_work_items_for_code_analysis_warnings)  
  
- [Hledání a filtrování výsledků analýzy kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md#BKMK_Search)  
  
## <a name="BKMK_ConfigureRuleSets"></a>Konfigurace sad pravidel pro projekt  
  
1. V **Průzkumník řešení**otevřete místní nabídku pro název projektu a pak zvolte možnost **vlastnosti**.  
  
2. Následující kroky jsou volitelné:  
  
    1. V seznamech **Konfigurace** a **platforma** vyberte konfigurace sestavení a cílová platforma.  
  
    2. Ve výchozím nastavení analýza kódu sestavu upozornění z kódu, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění z vygenerovaného kódu, zrušte zaškrtnutí políčka **Potlačit výsledky z vygenerovaného kódu** .  
  
        > [!NOTE]
        > Tato možnost není potlačit chyby analýzy kódu a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Zdrojový kód formuláře nebo šablony můžete zobrazit a spravovat.  
  
3. Chcete-li spustit analýzu kódu pokaždé, když je projekt sestaven pomocí vybrané konfigurace, zaškrtněte políčko **Povolit analýzu kódu proC++ sestavení C/on** . Analýzu kódu lze také spustit ručně otevřením nabídky **analyzovat** a následným výběrem možnosti **Spustit analýzu kódu v** *ProjectName*.  
  
4. V seznamu **Spustit tuto sadu pravidel** proveďte jednu z následujících akcí:  
  
    - Vyberte sadu pravidel, kterou chcete použít.  
  
    - Vyberte **\<Procházet... >** k určení existující sady vlastních pravidel, která není v seznamu.  
  
    - Definujte vlastní sadu pravidel.  
  
         Další informace najdete v tématu [vytváření vlastních sad pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
### <a name="standard-cc-rule-sets"></a>Standardní sady CC++ /pravidla  
 Sada Visual Studio obsahuje dvě standardní sady pravidel pro nativní kód:  
  
|Sada pravidel|Popis|  
|--------------|-----------------|  
|Nativní minimální doporučená pravidla společnosti Microsoft|Tato sada pravidel se zaměřuje na nejdůležitější problémy v nativním kódu, včetně možných bezpečnostních děr a chyb aplikací. Tuto sadu pravidel byste měli zahrnout v jakékoli vlastní sadě pravidel, kterou vytvoříte pro vaše nativní projekty.|  
|Nativní doporučená pravidla společnosti Microsoft|Tato sada pravidel se zabývá širokou škálou problémů. Obsahuje všechna pravidla pro nativní minimální doporučená pravidla společnosti Microsoft.|  
  
## <a name="BKMK_Run"></a>Spustit analýzu kódu  
 Na stránce Analýza kódu na stránkách vlastností projektu můžete nakonfigurovat analýzu kódu, která se spustí při každém sestavení projektu. Můžete také spustit analýzu kódu ručně.  
  
 Spuštění analýzy kódu v řešení:  
  
- V nabídce **sestavení** vyberte možnost **Spustit analýzu kódu v řešení**.  
  
  Spuštění analýzy kódu v projektu:  
  
- V Průzkumník řešení vyberte název projektu.  
  
- V nabídce **sestavení** vyberte možnost **Spustit analýzu kódu pro** *název projektu*.  
  
  Projekt nebo řešení jsou kompilovány a je spuštěna analýza kódu. Výsledky se zobrazí v okně analýzy kódu.  
  
## <a name="BKMK_Analyze"></a>Analyzovat a vyřešit upozornění analýzy kódu  
 Pokud chcete analyzovat konkrétního upozornění, vyberte záhlaví upozornění v okně analýzy kódu. Upozornění se rozbalí, aby se zobrazily další informace o problému. Pokud je to možné, analýza kódu zobrazuje čísla řádků a logiku analýzy, která vedla k upozornění. Pokud chcete zobrazit podrobné informace o upozornění, včetně možných řešení problému, vyberte ID upozornění, abyste zobrazili téma nápovědy v knihovně MSND pro danou zprávu.  
  
 Při rozšiřování upozornění na řádek kódu, který způsobil toto upozornění je zvýrazněn v editoru kódu sady Visual Studio.  
  
 Po zjištění problému ho mohli vyřešit ve vašem kódu. Pak znovu spusťte analýzu kódu, abyste měli jistotu, že již nezobrazuje upozornění v okně analýzy kódu, a nová upozornění, že jste kód opravili správně nebyla vyvolána.  
  
> [!TIP]
> Můžete znovu spustit analýzu kódu v okně analýzy kódu. Klikněte na tlačítko **analyzovat** a vyberte rozsah analýzy. Můžete znovu spustit analýzu na celé řešení nebo vybraný projekt.  
  
## <a name="BKMK_Suppress"></a>Potlačení upozornění analýzy kódu  
 Existují situace, kdy byste se mohli rozhodnot Neopravovat upozornění analýzy kódu. Můžete se rozhodnout, že řešení upozornění vyžaduje příliš mnoho nahrávání ve vztahu k pravděpodobnost, že problém vzniknou v žádné Skutečná implementace kódu. Nebo může domnívat, že je nevhodná pro konkrétní kontext, který se používá v tomto upozornění analýzy. Jednotlivá upozornění můžete potlačit tak, aby se nebude zobrazovat v okně analýzy kódu.  
  
 Chcete-li potlačit upozornění:  
  
1. Pokud se nezobrazují podrobné informace, vyberte název upozornění a rozbalte ho.  
  
2. V dolní části upozornění klikněte na odkaz **Akce** .  
  
3. Zvolte možnost **potlačit zprávu** a pak zvolte možnost **zdroj**.  
  
   Potlačení vkládání zprávy `#pragma warning (disable:`*WarningId*`)`, které potlačí upozornění na řádek kódu.  
  
## <a name="BKMK_Creating_work_items_for_code_analysis_warnings"></a>Vytváření pracovních položek pro upozornění analýzy kódu  
 Funkci sledování pracovní položky můžete použít k protokolování chyb z aplikace Visual Studio. Chcete-li použít tuto funkci, je nutné se připojit k instanci Team Foundation Server.  
  
 **Vytvoření pracovní položky pro jedno nebo více upozornění C/C++ kódu**  
  
1. V okně Analýza kódu rozbalte a vyberte upozornění.  
  
2. V místní nabídce pro upozornění zvolte **vytvořit pracovní položku**a pak zvolte typ pracovní položky.  
  
3. Visual Studio vytvoří jednu pracovní položku pro vybraná upozornění a zobrazí pracovní položku v okně dokumentu integrovaného vývojového prostředí (IDE).  
  
4. Přidejte další informace a pak zvolte **Uložit pracovní položku**.  
  
## <a name="BKMK_Search"></a>Hledání a filtrování výsledků analýzy kódu  
 Můžete hledat dlouhé seznamy varovné zprávy a upozornění v řešení vícenásobného projektu můžete filtrovat.  
  
1. **Filtrování upozornění podle názvu nebo ID upozornění**: zadejte klíčové slovo do textového pole **Filter** .  
  
2. **Chcete-li filtrovat upozornění podle projektu**: v řešení více projektů, vyberte jeden nebo více projektů v seznamu v pravém horním rohu okna Analýza kódu. Chcete-li zobrazit všechna upozornění, vyberte název řešení.  
  
3. **Filtrování upozornění podle závažnosti**: ve výchozím nastavení se zprávám analýzy kódu přiřadí závažnost **Upozornění**. Závažnost jedné nebo více zpráv můžete přiřadit jako **chybu** v sadě vlastních pravidel. Chcete-li zobrazit pouze zprávy, které jsou přiřazeny příslušné závažnosti, vyberte možnost **Upozornění** nebo **Chyba** . Výběrem možnosti **vše** zobrazíte všechny zprávy.
