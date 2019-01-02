---
title: 'Průvodce: Zaznamenání grafických informací | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5dc2da1aec6c2e819e5d39287ac1c43f72ce8e27
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938890"
---
# <a name="walkthrough-capturing-graphics-information"></a>Průvodce: Zaznamenání grafických informací
Tento návod ukazuje, jak používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] diagnostiky grafiky k ručně zachytit informace grafiky z aplikace Direct3D.  
  
 Tento návod ilustruje tyto úkoly:  
  
-   Zachycení diagnostiky grafiky do vaší aplikace  
  
-   Zachycení informací grafiky  
  
## <a name="capturing-graphics-information"></a>Zachycení informací grafiky  
 Použití nástrojů diagnostiky grafiky, je nejprve nutné zachytit informace grafiky, která ho využívá. K povolení funkce capture, použijte **spustit diagnostiku** příkaz, který připojí nástroj Diagnostika grafiky do vaší aplikace při spuštění.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Chcete-li povolit zachycení informací grafiky po projekt nebo řešení je načteno  
  
1. V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načtení souboru projektu nebo řešení pro aplikaci, kterou chcete zachytit informace grafiky z.  
  
2. Na panelu nástrojů diagnostiky grafiky **spustit diagnostiku**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Chcete-li povolit zachycení informací grafiky bez načítání projektu nebo řešení  
  
1. V panelu nabídky zvolte **souboru**, **otevřít**, **projekt či řešení**. **Otevřít projekt** zobrazí se dialogové okno.  
  
2. Místo souboru projektu nebo řešení, zadejte spustitelný soubor pro aplikaci, kterou chcete zachytit informace grafiky z a klikněte na tlačítko **otevřít**.  
  
3. V panelu nabídky zvolte **ladění**, **grafiky**, **spustit diagnostiku**.  
  
   Po spuštění aplikace a je vykreslování rámce, může zachytit grafické informace.  
  
#### <a name="to-capture-graphics-information"></a>Chcete-li zachytit informace grafiky  
  
- Na panelu nástrojů diagnostiky grafiky **zachycení** tlačítko. ![Zachytávání grafiky ikonu tlačítka](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
   -nebo-  
  
   S aplikací fokus, stiskněte klávesu **Print Screen**.  
  
  Pokaždé, když zaznamenat informace o snímek, diagnostiky grafiky zaznamenává události rozhraní Direct3D a přidružený stav a přidá tato data do protokolu grafiky. Pro každou relaci diagnostiky grafiky je vytvořen nový protokol grafiky. Informace o protokoly grafiky, naleznete v tématu [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Další kroky  
 Tento názorný postup ukázal, jak lze zachytit informace grafiky ručně. V dalším kroku vezměte v úvahu tuto možnost:  
  
-   Zjistěte, jak analyzovat zachycené informace grafiky pomocí nástrojů diagnostiky grafiky. Zobrazit [přehled](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Viz také  
 [Zaznamenání grafických informací](capturing-graphics-information.md)