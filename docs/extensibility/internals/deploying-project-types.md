---
title: Nasazování typů projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 358ab66ecf1f3602ce37f85de803bd8953771858
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53892130"
---
# <a name="deploy-project-types"></a>Nasazování typů projektů
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] nainstaluje nový agregátor typu projektu (*ProjectAggregator2.dll*) a také balíček Instalační služby systému Windows pro automatické distribuce signatur (*ProjectAggregator2.msi*). Je nutné použít nový agregátor pro typy projektů spravovaného kódu. ProjectAggregator2 obejde omezení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu agregátorem, který brání typy projektů spravovaný kód podle vašich představ. Následující kroky popisují, jak změnit vašeho balíčku VSPackage pro použití se novému agregátoru.  
  
1.  Odeberte projekt NativeHierarchyWrapper z vašeho řešení.  
  
2.  Odebrání binárních souborů NativeHierarchyWrapper vašeho nastavení.  
  
3.  Přidat *ProjectAggregator2.msi* do vašeho nastavení.