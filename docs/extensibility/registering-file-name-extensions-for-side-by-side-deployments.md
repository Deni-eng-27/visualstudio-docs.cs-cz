---
title: Registrace přípony názvů souborů pro nasazení vedle sebe | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a21c4f330d78d35735cb8463af62802d1fa21a4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961660"
---
# <a name="register-file-name-extensions-for-side-by-side-deployments"></a>Registrace přípony názvů souborů pro nasazení vedle sebe
Pro balíčky VSPackages nasazení v prostředí vedle sebe, je nutné zaregistrovat přípony názvů souborů pro přidružení souborů k správnou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pokud nechcete použít příponu názvu souboru specifické pro verzi, registrace umožňuje uživatelům otevřete svůj projekt a projekt soubory položek v příslušné verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [O přípony názvů souborů](../extensibility/about-file-name-extensions.md)  
 Tento článek popisuje způsob registrace přípony názvů souborů.  
  
 [Určení popisovačů souborů pro přípony názvů souborů](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 Poskytuje informace o postupu při registraci aplikace, které můžete otevřít, upravit a tak dále, konkrétní příponu.  
  
 [Registrace operací pro přípony názvů souborů](../extensibility/registering-verbs-for-file-name-extensions.md)  
 Tento článek popisuje postup registrace příkazů.  
  
 [Správa přidružení souborů vedle sebe](../extensibility/managing-side-by-side-file-associations.md)  
 Tento článek popisuje způsob zpracování-souběžnými instalacemi, ve kterém konkrétní verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] by mělo být vyvoláno pro otevření souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podpora více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 Popisuje problémy spojené s více verzemi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vaše VSPackage během vývoje a nasazení tak, aby koncoví uživatelé.