---
title: 'Návod: Příklad LinqToXmlDataBinding | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 54e714aa95ee1206e278546bcd61e31687c45211
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182282"
---
# <a name="walkthrough-linqtoxmldatabinding-example"></a>Návod: Příklad LinqToXmlDataBinding
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento návod popisuje příklad LinqToXmlDataBinding a vysvětluje některé zajímavější obsah jeho dvě primární zdrojové soubory, L2DBForm.xaml a L2DBForm.xaml.cs.  
  
## <a name="prerequisites"></a>Požadavky  
 Předtím, než se pustíte do čtení tohoto návodu, důrazně doporučujeme sestavit a spustit LinqToXmlDataBinding program, jak je popsáno v [postupy: vytvoření a spuštění příkladu Linqtoxmldatabinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md).  
  
## <a name="remarks"></a>Poznámky  
 LinqToXmlDataBinding program je aplikace Windows Presentation Foundation (WPF), který se skládá C# a XAML zdrojové soubory. Obsahuje vložený dokument XML, který definuje seznam knihy a umožňuje uživatelům zobrazit, přidat, odstranit a upravit tyto položky. Se skládá z následujících dvou primární zdrojové soubory:  
  
-   L2DBForm.XAML obsahuje kód XAML deklarace pro uživatelské rozhraní (UI) hlavního okna. Obsahuje také oddíl prostředků okna, která definuje data provider a vloženého dokumentu XML pro výpisy knihy.  
  
-   L2DBForm.XAML.cs obsahuje inicializační a metody zpracování událostí, které jsou přidružené uživatelské rozhraní.  
  
 Hlavní okno je rozdělen do následujících čtyř svislé částí uživatelského rozhraní:  
  
-   **XML** zobrazí nezpracovaný zdroj dat XML vložené adresáře seznamu.  
  
-   **Rezervuje seznamu** zobrazuje jako standardní text položky adresáře a umožňuje uživateli vybrat a odstranit jednotlivé položky.  
  
-   **Upravit vybrané knihy** umožňuje uživateli upravit hodnoty přidružené k položce vybrané knihy.  
  
-   **Přidat nový adresář** umožňuje vytvořit novou položku seznamu na základě hodnot zadaných uživatelem.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Zdrojový kód L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md)|Obsahuje obsah a popis kódu XAML v souboru L2DBForm.xaml.|  
|[Zdrojový kód L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md)|Obsahuje obsah a popis zdrojový kód C# v souboru L2DBForm.xaml.cs.|  
  
## <a name="see-also"></a>Viz také  
 [Datové vazby WPF pomocí LINQ to XML příklad](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [Postupy: Sestavení a spuštění příkladu LinqToXmlDataBinding](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)



