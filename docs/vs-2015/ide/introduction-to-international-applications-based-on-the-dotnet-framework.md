---
title: Seznámení s mezinárodními aplikacemi na základě .NET Framework | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- strings [Visual Studio], localizing
- Web applications [.NET Framework], globalization
- Windows Forms, globalization
- localization [Visual Studio], culture setting
- fallback resources
- culture, setting
- globalization [Visual Studio], culture setting
- resources [Visual Studio], localization
- localization [Visual Studio], .NET localization model
- Assembly Resource file template
- resources [Visual Studio], fallback system
- international applications [Visual Studio], about international applications
- globalization [Visual Studio], international applications
- ASP.NET, globalization
- resource files, fallback processes
- user interface, culture setting
ms.assetid: b0788993-e62d-4f68-8235-5f87b1d48525
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0d57cee8591196d12e51e58fb0e5e6a4a2cdf94a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75848365"
---
# <a name="introduction-to-international-applications-based-on-the-net-framework"></a>Představení mezinárodních aplikací založených na prostředí .NET Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V produktu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] jsou k dispozici dvě části pro vytvoření špičkové aplikace: globalizace, proces navrhování aplikací, které mohou být přizpůsobeny různým kulturám a lokalizaci, proces překladu prostředků pro konkrétní jazykovou verzi. Obecné informace o navrhování aplikací pro mezinárodní cílovou skupinu najdete v tématu [osvědčené postupy pro vývoj aplikací připravených](https://msdn.microsoft.com/library/f08169c7-aad8-4ec3-9a21-9ebd3b89986c)pro použití ve světě.

 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]Model lokalizace se skládá z hlavního sestavení, které obsahuje kód aplikace a záložní prostředky – řetězce, obrázky a další objekty pro jazyk, ve kterém je aplikace původně vyvinuta. Každá lokalizovaná aplikace bude mít satelitní sestavení nebo sestavení, která obsahují pouze lokalizované prostředky. Vzhledem k tomu, že hlavní sestavení vždy obsahuje záložní prostředky, pokud prostředek nebyl nalezen v lokalizovaném satelitním sestavení, <xref:System.Resources.ResourceManager> pokusí se ho načíst hierarchicky způsobem, nakonec se vrátí k prostředku v hlavním sestavení. Záložní systém prostředků je podrobněji vysvětlen v [hierarchické organizaci prostředků k lokalizaci](../ide/hierarchical-organization-of-resources-for-localization.md).

 Jedním z prostředků lokalizace, které byste měli zvážit, je Glosář všech lokalizovaných produktů společnosti Microsoft. Tento soubor CSV obsahuje více než 12 000 anglických podmínek a překlady podmínek až do 59 různých jazyků. Glosář je k dispozici ke stažení na webové stránce [překlady terminologie společnosti Microsoft](https://msdn.microsoft.com/goglobal/bb688105.aspx) .

 Projektový systém pro model Windows Forms aplikace může generovat soubory prostředků pro záložní i každou požadovanou jazykovou verzi uživatelského rozhraní. Záložní soubor prostředků je integrován do hlavního sestavení a soubory prostředků specifické pro jazykovou verzi jsou pak integrovány do satelitních sestavení, jeden pro každou jazykovou verzi uživatelského rozhraní. Při sestavování projektu jsou soubory prostředků kompilovány z formátu XML sady Visual Studio (. resx) do mezilehlého binárního formátu (. Resources), které jsou poté vloženy do satelitních sestavení.

 Projektový systém pro model Windows Forms i webové formuláře umožňuje vytvářet soubory prostředků pomocí šablony souboru prostředků sestavení, přístupu k prostředkům a sestavení projektu. Satelitní sestavení budou vytvořena společně s hlavním sestavením.

 Když se spustí lokalizovaná aplikace, její vzhled je určen dvěma hodnotami kultury. ( *Jazyková verze* je sada informací o uživatelských preferencích souvisejících s jazykem, prostředím a kulturním konvencím uživatele.) Nastavení jazykové verze uživatelského rozhraní určuje, které prostředky budou načteny. Jazyková verze uživatelského rozhraní je nastavena jako `UICulture` v Web.config soubory a direktivy stránky a <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> v kódu Visual Basic nebo Visual C#. Nastavení jazykové verze určuje formátování hodnot, jako jsou data, čísla, měna a tak dále. Jazyková verze je nastavena jako `Culture` v Web.config soubory a direktivy stránky, <xref:System.Globalization.CultureInfo.CurrentCulture%2A> v Visual Basic nebo kódu jazyka Visual C#.

## <a name="see-also"></a>Viz také
 <xref:System.Globalization> <xref:System.Resources>
 [Globalizace a lokalizace zabezpečení aplikací](../ide/globalizing-and-localizing-applications.md) [a lokalizovaných satelitních sestavení](../ide/security-and-localized-satellite-assemblies.md)
