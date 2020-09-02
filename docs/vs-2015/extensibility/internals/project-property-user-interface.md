---
title: Uživatelské rozhraní vlastnosti projektu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 31840c40f2a494ffd32f5241e2770938138877e9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "65704089"
---
# <a name="project-property-user-interface"></a>Uživatelské rozhraní vlastností projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Podtyp projektu může použít položky v dialogovém okně **stránky vlastností** projektu, protože jsou dodány základním projektem, skrývat nebo provádět ovládací prvky jen pro čtení a celé stránky jako dodané nebo přidat stránky pro konkrétní projekt v dialogovém okně **stránky vlastností** .  
  
## <a name="extending-the-project-property-dialog-box"></a>Rozšíření dialogového okna vlastností projektu  
 Podtyp projektu implementuje objekty pro automatizaci automatizace a objekty pro procházení konfigurace projektu. Tyto rozšířené implementace implementují <xref:EnvDTE.IFilterProperties> rozhraní, aby určité vlastnosti byly skryté nebo jen pro čtení. Dialogové okno **stránky vlastností** základního projektu implementovaného základním projektem respektuje filtrování prováděné pomocí rozšířených objektů automatizace.  
  
 Následující postup je popsaný v části proces rozšíření **vlastností projektu** :  
  
- Základní projekt načte rozšířené typy z podtypu projektu implementací <xref:EnvDTE80.IInternalExtenderProvider> rozhraní. Všechny objekty základního projektu, které implementují toto rozhraní, jsou v procházení, automatizaci projektů a v konfiguraci projektu.  
  
- Implementace <xref:EnvDTE80.IInternalExtenderProvider> pro objekt procházení projektu a delegáta objektu automatizace projektu pro <xref:EnvDTE80.IInternalExtenderProvider> implementaci Agregátoru podtypu projektu (to znamená `QueryInterface` pro <xref:EnvDTE80.IInternalExtenderProvider> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt projektu).  
  
- Základní objekt pro procházení konfigurace projektu také implementuje <xref:EnvDTE80.IInternalExtenderProvider> přímý přenos z objektu konfigurace podtypu projektu přímo do zařízení. Jeho implementace deleguje <xref:EnvDTE80.IInternalExtenderProvider> rozhraní implementované Agregátorem podtypu projektu.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>, implementované objektem procházení konfigurace projektu, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>, který je implementován také objektem procházení konfigurace projektu, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> objekt.  
  
- Podtyp projektu může určit vhodné CATID pro různé objekty, které jsou v běhu základního projektu, načtením následujících <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> hodnot:  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  Pro určení CATID pro rozsah projektu načte podtyp projektu výše uvedené vlastnosti pro <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>  z `VSITEMID``typedef` . Podtyp projektu může také chtít určit, které stránky **vlastností** dialogového okna se zobrazí pro projekt, jak závislé na konfiguraci, tak i na nezávisle na konfiguraci. Některé podtypy projektů mohou potřebovat odebrat předdefinované stránky a přidat konkrétní stránky podtypu projektu. Aby to bylo možné povolit, projekt spravovaného klienta volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> metodu pro následující vlastnosti:  
  
- `VSHPROPID_PropertyPagesCLSIDList` – středníkem oddělený seznam identifikátorů CLSID na stránkách vlastností nezávislých na konfiguraci.  
  
- `VSHPROPID_CfgPropertyPagesCLSIDList —` středníkem oddělený seznam identifikátorů CLSID na stránkách vlastností závislých na konfiguraci.  
  
  Vzhledem k tomu, že podtyp projektu agreguje <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt, může přepsat definici těchto vlastností, aby bylo možné určit, které dialogová okna **stránky vlastností** budou zobrazena. Podtyp projektu může načíst tyto vlastnosti z vnitřního základního projektu a pak podle potřeby přidávat nebo odebírat identifikátory CLSID.  
  
  Nové stránky vlastností přidané podtypu projektu jsou předány objektem pro procházení konfigurace projektu ze základní implementace projektu. Tento objekt pro procházení konfigurace projektu podporuje rozšířené služby automatizace. Další informace o AutomationExtenders najdete v tématu [implementace a používání zařízení s rozšířenými automatizace](https://msdn.microsoft.com/library/0d5c218c-f412-4b28-ab0c-33a611f62356). Stránky vlastností implementované voláním podtypu projektu <xref:EnvDTE.Project.Extender%2A> pro načtení vlastního objektu pro procházení konfigurace podtypu projektu, který rozšiřuje objekt procházení Konfigurace základního projektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE.IFilterProperties>   
 [Dialogové okno stránky vlastností](https://msdn.microsoft.com/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)
