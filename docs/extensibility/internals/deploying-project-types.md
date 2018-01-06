---
title: "Nasazení projektu typy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2171a940951d828df358d09dae5fec68b6475e4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-project-types"></a>Nasazení typy projektů
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]nainstaluje nový agregátor typu projektu (ProjectAggregator2.dll) a také balíček Instalační služby systému Windows pro opětovnou distribuci (ProjectAggregator2.msi). Je nutné použít nový agregátor pro typy projektů spravovaného kódu. ProjectAggregator2 funguje postupy omezení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu agregátoru, které zabrání typy projektů spravovaného kódu z funguje správně. Následující kroky popisují, jak chcete-li změnit váš VSPackage používat se novému agregátoru.  
  
1.  Projekt NativeHierarchyWrapper odeberte z vašeho řešení.  
  
2.  Odeberte všechny binární soubory NativeHierarchyWrapper z vašeho nastavení.  
  
3.  Přidejte ProjectAggregator2.msi do vašeho nastavení.