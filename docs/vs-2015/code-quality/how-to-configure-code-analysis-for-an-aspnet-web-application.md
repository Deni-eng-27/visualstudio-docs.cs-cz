---
title: 'Postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.asp
ms.assetid: b3000b31-fd9d-489e-81a2-a4bee49453ba
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8e75f5a584dd0522240f8b4d45cb28107bca38e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201399"
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V [!INCLUDE[vsPreShort](../includes/vspreshort-md.md)] a [!INCLUDE[vsUltShort](../includes/vsultshort-md.md)] můžete vybrat ze seznamu analýzy kódu *sad pravidel* vyrovnat [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] webovou aplikaci. Výchozí sada pravidel je Microsoft Minimální doporučená pravidla. Můžete vybrat jinou sadu pravidel, která platí pro webové stránky.  
  
### <a name="to-configure-a-rule-set-for-an-aspnet-page-framework-project"></a>Chcete-li konfigurovat sadu pravidel pro projekt rámec stránky ASP.NET  
  
1. Vyberte web v **Průzkumníka řešení**.  
  
2. Na **analyzovat** nabídky, klikněte na tlačítko **konfigurovat analýzu kódu pro webovou stránku**.  
  
3. Pokud jste vybrali řešení a řešení obsahuje více než jeden projekt, vyberte sestavení konfigurace a cílový operační systém z **konfigurace** a **platformy** seznamy.  
  
4. Pro každý projekt v řešení, klikněte na tlačítko **sady pravidel** sloupec a pak klikněte na název pravidla nastaven na spouštění.  
  
5. Ve výchozím nastavení je analýza kódu spuštěna na všechny projekty v řešení. Pokud chcete zakázat nebo povolit analýzu kódu pro konkrétní projekt, postupujte takto:  
  
    1. Klikněte pravým tlačítkem na název projektu a pak klikněte na vlastnosti.  
  
    2. Zaškrtněte nebo zrušte zaškrtnutí **povolit analýzu kódu** zaškrtávací políčko. Můžete také spustit analýzu kódu ručně tak, že vyberete **spustit analýzu kódu na webu** z **analyzovat** nabídky.  
  
6. V **spustit tuto sadu pravidel** rozevírací seznam, postupujte podle těchto kroků:  
  
    - Vyberte sadu pravidel, který chcete použít.  
  
    - Vyberte  **\<procházet >** zadat sadu existujících vlastních pravidel, která se nenachází v seznamu.  
  
    - Definujte vlastní sady pravidel. Další informace najdete v tématu [vytvoření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).
