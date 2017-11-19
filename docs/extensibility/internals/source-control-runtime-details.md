---
title: "Zdroj ovládacího prvku za běhu podrobnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9647f1f399b0d6516fe6475e6245c6834a0ea2b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="source-control-runtime-details"></a>Podrobnosti o modulu Runtime zdroj ovládacího prvku
Projekt je přidán do správy zdrojového kódu, pokud uživatel přidá soubor projektu do správy zdrojového kódu, nebo prostřednictvím řadič služby automation, například Průvodce. Projekt neurčuje pro sebe sama, že je ve správě zdrojového; podporuje zdrojového kódu, ale musí být přidaný do ji ručně.  
  
## <a name="registering-with-a-source-control-package"></a>Registrace balíčku zdroj ovládacího prvku  
 Když je soubor ve vašem projektu přidán do správy zdrojového kódu, prostředí volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> abyste si mohli čtyři neprůhledného řetězce, které jsou používány jako soubory cookie správy zdrojového kódu. Uložte tyto řetězce v souboru projektu. Tyto řetězce by měla být předána zdroj ovládacího prvku se zakázaným inzerováním (součást sady Visual Studio spravující zdroj ovládacího prvku balíčky) při spuštění typ projektu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>. To zase načte balíček řízení příslušné zdrojové a předává volání jeho implementace `IVsSccManager2::RegisterSccProject`.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)