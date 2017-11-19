---
title: "Vytvoření ovládacího prvku VSPackage zdroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4c3d414f1fcf6a7f4cd4155eb04e3696fb39740a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-source-control-vspackage"></a>Vytvoření ovládacího prvku VSPackage zdroje
Tato dokumentace obsahuje odkazy na přehled architektury správy zdroje balíčku integrovat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], rozhraní API, která je definována rozhraní k implementaci a služby, který se má používat a vzorku, který znázorňuje jednoduché zdroj řízení implementace balíčku.  
  
 Pomocí zdrojového kódu VSPackage můžete vytvářet těsná integrace cestu pro správy zdrojového kódu pro integraci s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Umožňuje, aby balíček, který chcete vynechat výchozí zdrojového kódu uživatelského rozhraní, které jsou hostované [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], reagovat na požadavky řízení zdroje ze systému projektu a interakci s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] součásti, jako **Průzkumníku řešení**. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Umožňuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] partnerům mechanismus pro vytvoření VSPackage, můžete integrovat se [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] použití modelu služby.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 Popisuje zdrojový balíček pro ovládací prvek, který pokročilejší alternativu k řízení zdrojů, modul plug-in pro implementaci funkcí správy zdrojového kódu v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Architektura](../../extensibility/internals/source-control-vspackage-architecture.md)  
 Uvede diagram a vysvětluje součásti balíčku zdroj ovládacího prvku.  
  
 [Funkce](../../extensibility/internals/source-control-vspackage-features.md)  
 Popisuje různé funkce řízení zdroje balíčku.  
  
 [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 Popisuje strukturu VSPackage, které se musí implementovat řízení balíček zdroje pro těsná integrace.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Popisuje postup vytvoření Správa zdrojového kódu modulu plug-in poskytující funkce správy zdrojového v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdroj ovládacího prvku uživatelského rozhraní (UI).  
  
 [Správa zdrojového kódu](../../extensibility/internals/source-control.md)  
 Popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].