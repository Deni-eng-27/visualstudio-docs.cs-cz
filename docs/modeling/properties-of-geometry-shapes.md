---
title: "Vlastnosti geometrické obrazce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 00897fa468ef223b523101810d1bbe7b8fa533fb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-geometry-shapes"></a>Vlastnosti geometrických obrazců
Geometrické obrazce můžete určit, jak jsou instance třídy domény zobrazí v jazyce specifické pro doménu. Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Geometrické obrazce mají vlastnosti, které jsou uvedeny v následující tabulce.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Barva výplně|Barva výplně tento tvar.|prázdné|  
|Zadejte režim přechodu|Režim barevného přechodu výplně tento tvar (vodorovné, svislé, předat dál diagonálních, zpětné diagonálních nebo None).|vodorovné|  
|Geometrie|Geometrie tento tvar (obdélníku, zaokrouhlí obdélníku, elipsy nebo kruhu).|rámeček|  
|Má výchozí body připojení|Pokud `True`tvar, který bude používat nahoru, dolů, doleva a správný připojovací body v Návrháři vygenerovaný.|False|  
|Barva obrysu|Obrysovou barvu tohoto tvaru.|černé|  
|Styl obrysu čárka|Styl obrysu dash tento tvar (ucelený, čárku, tečku, DashDot, DashDotDot nebo vlastní).|Plnou|  
|Tloušťka obrysu|Tloušťka obrysu tento tvar.|0.03125|  
|Barva textu|Barva, který se používá pro dekoratéry textu, které jsou přidruženy tento tvar.|černé|  
|Modifikátor přístupu|Modifikátor přístupu – třída (veřejné nebo interní).|Public|  
|Vlastní atributy|Použít k přidání atributů do třída zdroje kód, který se vygeneruje pro tento tvar.|\<none>|  
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modifikátor dědičnosti|Popisuje typ dědičnosti zdrojovou třídu kódu, která se generují z tvaru (`none`, `abstract` nebo `sealed`).|žádná|  
|Základní geometrické obrazce|Základní třída tento tvar.|(žádný)|  
|Název|Název tohoto tvaru.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený tento tvar.|Aktuální obor názvů|  
|ToolTip – typ|Jak popisek je definována (pevná, proměnné nebo žádný). Pokud odstraněna, pak hodnota `Fixed Tooltip Text` vlastnost se používá jako popisek; Pokud proměnné, pak popisek je definována v vlastní kód.|Žádné|  
|Poznámky|Neformální poznámky, které jsou spojeny s tímto elementem.|\<none>|  
|Počáteční výšku.|Počáteční výška tohoto tvaru, v palcích.|1|  
|Počáteční šířka|Počáteční šířka tohoto tvaru, v palcích.|1.5|  
|Barva výplně zveřejněné jako vlastnost<br /><br /> Režim zveřejněné vyplnění přechodu<br /><br /> Zveřejněné obrysovou barvu jako vlastnost<br /><br /> Styl obrysu Dash zveřejněné jako vlastnost<br /><br /> Vystavený Tloušťka obrysu jako vlastnost<br /><br /> Barva textu zpřístupňuje|Pokud `True`, může uživatel nastavit vlastnost stanovené obrazce. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na definici tvar a klikněte na **přidat zveřejněné**.|False|  
|Popis|Popis, který se používá k dokumentu generovaný návrháře.|\<none>|  
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tento tvar.|\<none>|  
|Opravené Text popisku|Text, který se používá pro pevnou popisek.|\<none>|  
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tento tvar.|\<none>|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)