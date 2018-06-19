---
title: Podpora více verzí sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 317ec1f214d18989c3b2c5c27fe9df9309239631
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137817"
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>Podpora více verzí sady Visual Studio
Termín *vedle sebe* znamená, že můžete nainstalovat a spravovat více verzí produktu na stejném počítači. Pro VSPackages, to znamená, že uživatel může mít několik verzí sady Visual Studio nainstalované na stejném počítači. Ale nemůže mít vedle sebe verze vaší VSPackages načíst do jediné verze sady Visual Studio.  
  
 Dříve, než vaše VSPackage moci být načtena do souběžně sdílená verze sady Visual Studio, zvažte následující:  
  
-   Je třeba určit strategii implementace vedle sebe, kterou chcete provést.  
  
     Další informace najdete v tématu [výběr mezi sdílené a verzí VSPackages](../extensibility/choosing-between-shared-and-versioned-vspackages.md).  
  
-   Vaše řešení a projektu formáty souborů se musí vejít strategie implementace.  
  
     Další informace najdete v tématu [upgrade projektů vlastní](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects) a [registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).  
  
-   Vaše instalační program musí zpracovávat strategie implementace tak, aby verzí a také komponenty sdílené mezi všemi verzemi správně nainstalovaný a zaregistrovaný.  
  
     Další informace najdete v tématu [instalaci VSPackages pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md) a také [správu součástí](../extensibility/internals/component-management.md).  
  
    > [!NOTE]
    >  Instalaci verze sady Visual Studio se nainstaluje také odpovídající verzi systému [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Například instalaci sady Visual Studio 2010 a Visual Studio 2012 na stejném počítači se nainstaluje také verze 4.0 a 4.5 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], v uvedeném pořadí.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Volba mezi sdíleným a verzovaným rozšířením VSPackages](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 Vysvětluje, jak řešit problémy vedle sebe v vaší VSPackage.  
  
 [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 Popisuje, jak vaše VSPackage registraci přidružení souborů ve scénáři vedle sebe.  
  
## <a name="related-sections"></a>Související oddíly  
 [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md)  
