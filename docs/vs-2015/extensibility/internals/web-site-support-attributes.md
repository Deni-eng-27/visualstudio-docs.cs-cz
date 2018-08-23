---
title: Atributy podpory webu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3fd60c1ffcb6bb4d3c386cf55fb1f33540bb3dd2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674846"
---
# <a name="web-site-support-attributes"></a>Atributy podpory webu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [atributy podpory webu](https://docs.microsoft.com/visualstudio/extensibility/internals/web-site-support-attributes).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Webový projekt je možné rozšířit o podporu pro webové programovacích jazyků. Jazyk musí registrovat s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tak, aby šablony projektů mohou objevit v **nový web** dialogové okno při výběru jazyka.  
  
 Ukázka IronPython Studio zahrnuje podporu webu. Můžete ho najít [VSSDK ukázky](../../misc/vssdk-samples.md). Obsahuje následující třídy atributů k registraci Ironpythonu jako codebehind jazyk pro nové webové projekty.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Tento atribut je umístěn v projektu jazyka. Přidá jazyk na seznam programovacích jazyků v oddílu Web **jazyk** v seznamu **nový web** dialogové okno. Například následující přidá IronPython do seznamu:  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Tento atribut nastaví také šablony cesty tak, aby odkazoval do složky šablony. Další informace o umístění složky šablony najdete v tématu [šablony podpory webu](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Tento atribut je umístěn v projektu jazyka. Webový projekt vnořit jeden typ souboru (související) umožňuje v rámci jiného typu souboru (primární) v **Průzkumníka řešení**.  
  
 Příklad:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Určuje, že soubor codebehind Ironpythonu vztahuje na soubor .aspx. Při vytvoření nové webové stránky .aspx v Ironpythonu webového řešení lokality nový zdrojový soubor .py se vygeneruje a zobrazí se jako podřízený uzel stránky ASPX.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Tento atribut je umístěn na balíčku projektu jazyka. Vybere poskytovatele technologie Intellisense pro jazyk.  
  
 Příklad:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 Určuje, že instance PythonIntellisenseProvider, která implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, by měl být vytvořen na vyžádání k poskytování služeb jazyka.  
  
 Implementace IVsIntellisenseProject zpracovává odkazy a volá kompilátor jazyka, pokud webové stránky s kódem je požadováno, ale neukládá do mezipaměti.  
  
## <a name="see-also"></a>Viz také  
 [Podpora webu](../../extensibility/internals/web-site-support.md)

