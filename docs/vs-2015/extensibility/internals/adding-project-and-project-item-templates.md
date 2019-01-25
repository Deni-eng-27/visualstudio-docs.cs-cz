---
title: Přidání projektu a šablony položek projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4b68c9f4bbaed73603c46fc0beab77a308b8933d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786261"
---
# <a name="adding-project-and-project-item-templates"></a>Přidávání šablon projektů a položek projektů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Když vytvoříte vlastní typy projektů, musíte poskytovat podporu pro přidání nové projekty a položky projektu pomocí standardní [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE) dialogových oknech. Následující témata popisují různé techniky pro přidání projektů a položek projektů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kontext projektu](../../extensibility/internals/project-context.md)  
 Tento článek vysvětluje, že projekt obsahuje většinu kontextové informace pro co ukáže v prostředí.  
  
 [Priorita projektu](../../extensibility/internals/project-priority.md)  
 Tento článek vysvětluje, že položka projektu je obvykle členem skupiny jednoho projektu, která pomáhá zabránit nejednoznačnost o tom, které se používá projekt, otevřete položku.  
  
 [Projekt Ostatní soubory](../../extensibility/internals/miscellaneous-files-project.md)  
 Poskytuje informace o dva typy editorů, které lze použít k otevření souborů v projektu a roli hraje projektu při určování, které editor pro použití při otevření položky projektu.  
  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)  
 Vysvětluje, co se stane, když [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] vytvoření projektu.  
  
 [Přidávání položek do dialogových oken Přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 Vysvětluje postup přidání položky, které chcete **přidat novou položku** dialogové okno.  
  
 [Přidávání adresářů do dialogového okna Nový projekt](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 Poskytuje příklad registrace nového adresáře, který obsahuje vlastní šablony, které jsou k dispozici společností VSPackage.  
  
 [Přidávání adresářů do dialogového okna Přidat novou položku](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 Poskytuje příklad novou sadu adresářů pro registraci **přidat novou položku** dialogové okno.  
  
 [Příkazy definované prostředím IDE pro rozšíření systémů projektů](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 Obsahuje seznam různých typů položek příkaz používá pro rozšíření systémů projektů.  
  
 [Identifikátory CATID pro objekty používané obvykle k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 Uvádí identifikátory CatID pro objekty, které se používají k rozšíření [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)], [!INCLUDE[csprcs](../../includes/csprcs-md.md)], a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] systémy projektů.  
  
## <a name="related-sections"></a>Související oddíly  
 [Postupy: Otevřít editoru pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md)  
 Obsahuje podrobné pokyny pro otevírání položky vnitřně vázaný na zvláštní editor pro projekt.  
  
 [Postupy: Otevřít standardních editorů](../../extensibility/how-to-open-standard-editors.md)  
 Obsahuje podrobné pokyny pro otevření standardní editor.  
  
 [Podtypy projektů](../../extensibility/internals/project-subtypes.md)  
 Obsahuje odkazy na koncepční témata podtyp projektu. Podtypy projektů rozšířit existující [!INCLUDE[csprcs](../../includes/csprcs-md.md)] a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] projekty.  
  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Obsahuje odkazy na další témata, která nabízí informace o navrhování nových typů projektů.
