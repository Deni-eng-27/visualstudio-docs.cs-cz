---
title: Možnosti uživatele řešení (. Suo) soubor | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- .suo files, VSPackages
- suo files, VSPackages
- solutions, .suo files
- solutions, user options
- solution user options (.suo) file
ms.assetid: 75258e0d-600d-4a3d-94f4-3d7ac12cb47c
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1a9825fabe08940e8950cf88a1dbf2bc149af0b2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68197328"
---
# <a name="solution-user-options-suo-file"></a>Soubor uživatelských možností řešení (.Suo)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Soubor možností uživatele řešení (. suo) obsahuje možnosti řešení pro jednotlivé uživatele. Tento soubor by neměl být vrácen se změnami do správy zdrojového kódu.  
  
 Soubor možností uživatele řešení (. suo) je strukturované úložiště nebo složený soubor uložený v binárním formátu. Informace o uživateli ukládáte do datových proudů s názvem datového proudu, který je klíčem, který bude použit k identifikaci informací v souboru. suo. Soubor možností uživatele řešení se používá k uložení nastavení uživatelských předvoleb a automaticky se vytvoří, když Visual Studio uloží řešení.  
  
 Když prostředí otevře soubor. suo, vytvoří výčet všech aktuálně načtených VSPackage. Pokud VSPackage implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> rozhraní, pak prostředí zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.LoadUserOptions%2A> metodu na VSPackage, která si ji vyžádá, aby načetla všechna svá data ze souboru. suo.  
  
 Je zodpovědností VSPackage, jak zjistit, které datové proudy mohly být zapsány do souboru. suo. Pro každý datový proud, který napsal, rozhraní VSPackage volá do prostředí a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> načte konkrétní datový proud, který je identifikován klíčem, což je název datového proudu. Prostředí pak zavolá zpět do VSPackage a přečte tento konkrétní proud, který předává název datového proudu a `IStream` ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> metodu.  
  
 V tomto okamžiku je provedeno jiné volání, aby `LoadUserOptions` bylo možné zjistit, zda existuje jiný oddíl souboru. suo, který má být načten. Tento proces pokračuje, dokud nebudou všechny datové proudy v souboru. suo načteny a zpracovány prostředím.  
  
 Když je řešení uloženo nebo zavřeno, prostředí volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.SavePackageSolutionProps%2A> metodu s ukazatelem na <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.SaveUserOptions%2A> metodu. `IStream`Do metody, která obsahuje binární informace, které mají být uloženy, se předává <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.WriteUserOptions%2A> metoda, která pak zapisuje informace do souboru. suo a volá `SaveUserOptions` metodu znovu, aby se zobrazila informace o tom, zda k zápisu do souboru. suo existuje jiný datový proud.  
  
 Tyto dvě metody, `SaveUserOptions` a `WriteUserOptions` , se nazývají rekurzivní pro každý datový proud informací, které mají být uloženy do souboru. suo, předáním ukazatele na `IVsSolutionPersistence` . Jsou volány rekurzivně, aby umožňovaly zápis více datových proudů do souboru. suo. V takovém případě jsou informace o uživateli trvale uložené v řešení a při příštím otevření řešení je zaručeno, že bude k dispozici.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 [Řešení](../../extensibility/internals/solutions-overview.md)
