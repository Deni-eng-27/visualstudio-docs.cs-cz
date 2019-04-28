---
title: Přehled jazyka specifického pro doménu nástrojů uživatelského rozhraní | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: overview
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 73d515c03b7966e3434a2fc2507d3ad5f8d13c1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569099"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Přehled uživatelského rozhraní Jazykových nástrojů specifických pro doménu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když poprvé otevřete řešení v nástroje jazyka specifického pro doménu (DSL Tools) [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], uživatelské rozhraní bude vypadat podobně jako na následujícím obrázku.  
  
 ![dsl designer](../modeling/media/dsl-designer.png "dsl_designer")  
  
 Následující tabulka vysvětluje, jak se používají částí uživatelského rozhraní.  
  
|**Element**|**Definice**|  
|-----------------|--------------------|  
|diagram|Diagram zobrazuje doménový model.<br /><br /> Diagram má dvě strany. Jedna strana definuje typy prvků ve vašich modelech. Druhé straně definuje, jak vaše modely se zobrazí na obrazovce.|  
|Sada nástrojů|Přetáhněte nástroje z panelu nástrojů přidejte doménovými třídami a obrazce typy do diagramu. Chcete-li přidat vztahy, konektory a mapy obrazců, klikněte na nástroje a pak klikněte na zdrojový uzel v diagramu a cílový uzel.|  
|Průzkumník modelu DSL|**Průzkumník modelu DSL** se zobrazí, když je aktivní okno Definice DSL. Jako strom zobrazuje DSL. Průzkumník modelu DSL umožňuje upravit funkce modelu, které nejsou zobrazeny v diagramu. Například můžete přidat položky panelu nástrojů a přepnout na proces ověření pomocí **Průzkumník DSL**.|  
|Okno podrobností DSL|**Podrobnosti DSL** okno zobrazuje vlastnosti domény prvky modelu, které umožňují řídit způsob zobrazení prvků, a jak jsou prvky zkopírovat a odstranit.<br /><br /> – Ve výchozím nastavení **podrobnosti DSL** okna se zobrazí vedle **seznam chyb** a **výstup** systému windows.|  
  
## <a name="the-domain-model-diagram"></a>Diagram modelu domény  
 Diagram modelu domény je rozdělena na dva oddíly. Straně diagram zobrazuje prvky a vztahy v modelu. Druhé straně ukazuje, jak je model, který se má zobrazit a zahrnuje tvary, které se používají k zobrazení prvky a vlastnosti diagramu modelu. Následující obrázek ukazuje prvky diagramu.  
  
 ![Návrhář DSL s plavecké dráhy](../modeling/media/dsl-desinger.png "dsl_desinger")  
  
 Následující tabulka popisuje některé prvky diagramu modelu domény.  
  
|**Termín**|**Definice**|  
|--------------|--------------------|  
|Domain Class|Doménové třídy jsou typy prvků ve vašich modelech.<br /><br /> Doménová třída může objevit více než jednou v diagramu, pokud je cílem více než jedna relace.<br /><br /> Chcete-li přidat doménovou třídou, přetáhněte nástroj třídy domény z **nástrojů** k **třídám a vztahům** diagramu vedle sebe.|  
|Doménový vztah|Doménové vztahy jsou typy odkazů mezi prvky ve vašich modelů.<br /><br /> *Vztah obsažení* označuje, že cílový element je ve vlastnictví nebo obsažená v tomto elementu zdroje a zobrazí se jako plná čára. Každý prvek v modelu by měla být cílem jeden vztah obsažení, tak, aby model tvoří strom. A *odkazovat na relaci* označuje obecné propojení prvků modelu a zobrazí se bude zobrazovat jako přerušovaná čára. Libovolný prvek může mít libovolný počet referenční odkazy.<br /><br /> Vytvoření relace po kliknutí na nástroj **nástrojů**, kliknutím na zdrojové doménové třídy a pak levým na cílové třídy.|  
|Obrazců a konektorů|Tvary určit, jak mají být zobrazeny prvky modelu na diagram DSL., konektory určit řádky v diagramu DSL, který slouží k zobrazení relací.<br /><br /> Chcete-li vytvořit obrazec nebo spojnici, přetáhněte nástroj, který **elementů diagramu** diagramu vedle sebe.|  
|Mapy obrazců|Mapa obrazce se zobrazí jako řádek na diagram modelu domény propojení doménová třída, která se zobrazí obrazec nebo spojnici na doménový vztah, který se zobrazí.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástrojů jazyka specifického pro doménu](../modeling/overview-of-domain-specific-language-tools.md)   
 [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md)
