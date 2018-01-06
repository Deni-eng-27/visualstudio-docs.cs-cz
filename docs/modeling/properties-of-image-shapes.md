---
title: "Vlastnosti bitové kopie tvarů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords: Domain-Specific Language, image shape
ms.assetid: 9ce00ccd-07f2-4640-ac96-2a60481d0d72
caps.latest.revision: "25"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 72e64d9a0e254ce34cea76eca8617dee71573dd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="properties-of-image-shapes"></a>Vlastnosti obrazových obrazců
Tvary bitové kopie můžete použít k určení, jak třídy domény se zobrazí v generované návrháře. Definování obrazce image nastavením `Image` vlastnost třídy do souboru předdefinované bitové kopie. Jsou podporovány následující formáty:  
  
-   .GIF  
  
-   .jpg  
  
-   .JPEG  
  
-   .bmp  
  
-   WMF  
  
-   .EMF  
  
-   soubor ve formátu PNG  
  
 Ve výchozím nastavení jsou soubory Návrháře prostředků, jako jsou soubory obrázků, nachází v **prostředky**složku **Dsl** projektu.  
  
 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Obrázek obrazce mají vlastnosti, které jsou uvedeny v následující tabulce.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Barva výplně|Barva výplně tento tvar.|prázdné|  
|Zadejte režim přechodu|Režim vyplnění přechodu tohoto tvaru.|vodorovné|  
|Má výchozí body připojení|Pokud `True`tvar, který bude používat nahoru, dolů, doleva a správný připojovací body v Návrháři vygenerovaný.|False|  
|Barva obrysu|Obrysovou barvu tohoto tvaru.|černé|  
|Styl obrysu čárka|Styl obrysu dash tento tvar (ucelený, čárku, tečku, DashDot, DashDotDot nebo vlastní).|Plnou|  
|Tloušťka obrysu|Tloušťka obrysu tento tvar.|0.03125|  
|Barva textu|Barva, který se používá pro dekoratéry textu, které jsou přidruženy tento tvar.|černé|  
|Modifikátor přístupu|Modifikátor přístupu geometrické obrazce (veřejné nebo interní).|Public|  
|Vlastní atributy|Použít k přidání atributů do zdrojového kódu třídu, která se generují z tento tvar.|\<žádné >|  
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modifikátor dědičnosti|Popisuje typ dědičnosti zdrojovou třídu kódu, která se generují z bitové kopie tvaru (`none`, `abstract` nebo `sealed`).|žádná|  
|Základní Image obrazce|Základní třída tento tvar.|(žádný)|  
|Název|Název tohoto tvaru.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený tento tvar.|Aktuální obor názvů|  
|ToolTip – typ|Místo, na kterých byla definována popisek (pevná, proměnné nebo žádný). Pokud odstraněna, pak hodnota `Fixed Tooltip Text` vlastnost se používá jako popisek; Pokud proměnné, pak popisek je definována v vlastní kód.|žádná|  
|Poznámky|Neformální poznámky, které jsou přidruženy tento tvar.|\<žádné >|  
|Počáteční výšku.|Úvodní výšce tohoto tvaru, v palcích.|1|  
|Počáteční šířka|Počáteční šířka tohoto tvaru, v palcích.|1.5|  
|Barva výplně zveřejněné jako vlastnost<br /><br /> Režim zveřejněné vyplnění přechodu<br /><br /> Zveřejněné obrysovou barvu jako vlastnost<br /><br /> Styl obrysu Dash zveřejněné jako vlastnost<br /><br /> Vystavený Tloušťka obrysu jako vlastnost<br /><br /> Barva textu zpřístupňuje|Pokud `True`, může uživatel nastavit vlastnost stanovené obrazce. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na definici tvar a klikněte na **přidat zveřejněné**.|False|  
|Popis|Používá k dokumentu generovaný návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tento tvar.|\<žádné >|  
|Opravené Text popisku|Text, který se používá pro pevnou popisek.|\<žádné >|  
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tento element.|\<žádné >|  
|Image|Cesta k souboru bitové kopie, který se používá pro tento tvar.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)