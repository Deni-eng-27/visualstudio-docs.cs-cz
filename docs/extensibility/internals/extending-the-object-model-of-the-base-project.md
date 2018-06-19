---
title: Rozšíření objektový Model základní projektu | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 9cffbecf585f6f8be4174531a91e466f65ab9a72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130554"
---
# <a name="extending-the-object-model-of-the-base-project"></a>Rozšíření objektový Model základní projektu

Podtyp projektu může rozšířit objektový model automatizace základní projektu na těchto místech:

-   Project.Extender ("\<ProjectSubtypeName >") – to umožňuje podtypem projektu na nabídku s vlastních metod z objektu <xref:EnvDTE.Project>. Podtyp projektu pomocí automatizace Extender lze zobrazit `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru dílčí hlavní projekt by měl nabízejí jeho objekt pro `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) CATID.

-   ProjectItem.Extender ("\<ProjectSubtypeName >") – to umožňuje podtypem projektu a nabídnout objekt s vlastních metod z konkrétní <xref:EnvDTE.ProjectItem> objekt v rámci projektu. Podtyp projektu pomocí automatizace Extender lze zobrazit tento objekt. <xref:EnvDTE80.IInternalExtenderProvider> Musí nabízejí jeho objekt pro rozhraní implementované v agregátoru dílčí hlavní projekt `VSHPROPID_ExtObjectCATID` z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídající požadované <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID.

-   Project.Properties - tuto kolekci zpřístupní vlastnosti konfigurace nezávislé `Project` objektu. Další informace o vlastnosti projektu najdete v tématu <xref:EnvDTE.Project.Properties%2A>. Podtyp projektu lze automatizace Extender do této kolekce přidat jeho vlastnosti. <xref:EnvDTE80.IInternalExtenderProvider> Musí nabízejí jeho objekt pro rozhraní implementované v agregátoru dílčí hlavní projekt `VSHPROPID_BrowseObjectCATID` z VSHPROPID2 (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>), z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID.

-   Configuration.Properties - tuto kolekci zpřístupní závislá na konfiguraci vlastnosti projektu pro konkrétní konfiguraci (například ladění). Další informace naleznete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu lze automatizace Extender do této kolekce přidat jeho vlastnosti. <xref:EnvDTE80.IInternalExtenderProvider> Rozhraní implementované v agregátoru dílčí hlavní projekt nabízí jeho objekt CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotu [VSITEMID. Kořenová](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Rozhraní se používá k rozlišení jeden objekt konfigurace procházet z jiné.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>