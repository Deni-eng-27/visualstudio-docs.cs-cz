---
title: "Zpětná vazba pro uživatele | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user model feedback
- environment, context
- IDE, context
- IDE, user feedback
ms.assetid: 2d472a24-3813-4f5f-9783-b491ad8a71ad
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3a5e31eb2acb50d9803bedd77e48d0821cbaea61
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="feedback-to-the-user"></a>Zpětná vazba pro uživatele
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE), vizuální zpětnou vazbu týkající k dispozici funkce je založena na aktuální výběr a globální výběr kontextu uživatele. Následující tabulka uvádí funkce, které jsou k dispozici v kontextech jiný výběr.  
  
|Výběr kontextu|Dostupné funkce|  
|-----------------------|-----------------------------|  
|IDE – integrované vývojové prostředí|Globální|  
|Aktuální sadu produktu|Specifické pro produkt|  
|Aktivní hierarchie|Konkrétní typ hierarchie|  
|Položka aktivní hierarchie|Konkrétní typ položky hierarchie|  
|Aktivní dokument|Konkrétní typ dokumentu|  
|Okno nejhornější rozhraní více dokumentů (MDI)|Konkrétní typ okna|  
|Aktuální výběr kontext|Výběr kontextu konkrétní|  
  
 Pokud jste pouze surface funkci uživatelé potřebovat a průběžně zadejte konzistentní výběr a zpětnou vazbu kontextu prostředí, můžete snížit složitost v prostředí IDE. Při každém otevření okna v prostředí IDE, platí následující pravidla:  
  
-   Pokud se okno změní jeho výběr kontextu, výběr zpětnou vazbu jasně uvedené v okně a okno dynamické nápovědy, zda se zobrazí, se aktualizuje tak, aby odrážela aktuální kontext.  
  
-   Pokud se okno změní globální výběr kontextu, všechny kontextové nabídky, okno active hierarchie a záhlaví aplikace jsou aktualizované, aby odrážela aktuální kontext.  
  
-   Okno by měl surface vlastnosti pro aktuální výběr v **vlastnosti** okno a volitelně, zda se zobrazí, **stránky vlastností** dialogové okno.  
  
-   Pokud okno nemá surface vlastnosti nebo kontext globální výběr změnit, výběr zpětné vazby by neměl zůstat v okně při již není aktivní okno v prostředí IDE.  
  
-   Všechny systémy windows specifické pro dokument nástroj průběžně odrážet aktivní dokument.  
  
-   Nabídek a panelů nástrojů záhlaví aplikace by měla odpovídat okna klienta nejhornější rozhraní více dokumentů (MDI).  
  
 Například když je otevřen zobrazení HTML webového formuláře do projektu webové aplikace Visual Basic a uživatel vybere `<td>` , zpětná vazba je zadána značka následujícím způsobem:  
  
-   Volba je uvedené v aktivní okno a promítnuta **vlastnosti** okno.  
  
-   Dokument specifické **sada nástrojů** aktualizován, aby odrážel aktivní dokument.  
  
-   **Editor** panelu nástrojů a **tabulky** nabídky se zobrazí a záhlaví aktualizuje tak, aby odrážela okna webového formuláře.  
  
-   Okno active hierarchii, což je většinou **Průzkumníku řešení**a jeho název panelu aktualizovat tak, aby odrážela aktuální kontext a kontextová **projektu** příkazy nabídky nyní budou vztahovat na web active Projekt aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Výběr a měny v prostředí IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [Výběr objektů kontextu](../../extensibility/internals/selection-context-objects.md)   
 [Hierarchie a výběr](../../extensibility/internals/hierarchies-and-selection.md)