---
title: Rozšíření objektového modelu základního projektu | Dokumentace Microsoftu
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e746ce8bf6d109d4cd1d96c531f30106f20d9c07
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882465"
---
# <a name="extend-the-object-model-of-the-base-project"></a>Rozšíření objektového modelu základního projektu

Podtyp projektu mohou rozšířit objektového modelu automatizace základního projektu na následujících místech:

-   Project.Extender ("\<ProjectSubtypeName >"): To umožňuje podtyp projektu nabízí objekt pomocí vlastní metody ze <xref:EnvDTE.Project> objektu. Podtyp projektu můžete použít zařízení Extender automatizace ke zveřejnění `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu by měl nabídnout jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) CATID.

-   ProjectItem.Extender ("\<ProjectSubtypeName >"): To umožňuje podtyp projektu nabízí objekt pomocí vlastní metody z konkrétní <xref:EnvDTE.ProjectItem> objekt v rámci projektu. Podtyp projektu můžete zveřejnit tento objekt použít zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídá požadovanou <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID.

-   Project.Properties: Tuto kolekci zpřístupní vlastnosti konfigurace nezávislé `Project` objektu. Další informace o `Project` vlastnosti, viz <xref:EnvDTE.Project.Properties%2A>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavního projektu je potřeba nabízejí jeho objekt pro `VSHPROPID_BrowseObjectCATID` z VSHPROPID2 (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>), z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID.

-   Configuration.Properties: Tato kolekce zpřístupní vlastnosti závislé na konfiguraci projektu pro konkrétní konfiguraci (například ladění). Další informace naleznete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu slouží k přidání vlastností do této kolekce zařízení Extender automatizace. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru podtyp hlavní projekt nabízí svého objektu pro CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotu [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Rozhraní se používá k rozlišení jednoho objektu procházet konfigurace z jiného.

## <a name="see-also"></a>Viz také:

<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>