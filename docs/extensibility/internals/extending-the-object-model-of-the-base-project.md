---
title: Rozšíření objektového modelu základního projektu | Microsoft Docs
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33186cd477ade7f562f6191393dabe8e94f4f194
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80708399"
---
# <a name="extend-the-object-model-of-the-base-project"></a>Rozšíří objektový model základního projektu.

Podtyp projektu může v následujících umístěních zvětšit objektový model automatizace základního projektu:

- Project. Extender (" \<ProjectSubtypeName> "): umožňuje dílčímu typu projektu nabízet objekt s vlastními metodami z <xref:EnvDTE.Project> objektu. Podtyp projektu může použít rozšířené automatizaci k vystavení `Project` objektu. <xref:EnvDTE80.IInternalExtenderProvider>Rozhraní implementované v Agregátoru podtypu hlavního projektu by mělo nabízet svůj objekt pro `VSHPROPID_ExtObjectCATID` od <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (odpovídající `itemid` hodnotě VSITEMID) [. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID.

- ProjectItem. Extender (" \<ProjectSubtypeName> "): umožňuje podtypu projektu nabízet objekt s vlastními metodami z konkrétního <xref:EnvDTE.ProjectItem> objektu v rámci projektu. Podtyp projektu může použít rozšířené automatizaci k vystavení tohoto objektu. <xref:EnvDTE80.IInternalExtenderProvider>Rozhraní implementované v hlavním Agregátoru podtypu projektu musí nabízet svůj objekt pro `VSHPROPID_ExtObjectCATID` od <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídající požadovanému <xref:Microsoft.VisualStudio.VSConstants.VSITEMID> ) CATID.

- Project. Properties: Tato kolekce zpřístupňuje vlastnosti objektu nezávislého na konfiguraci `Project` . Další informace o `Project` vlastnostech naleznete v tématu <xref:EnvDTE.Project.Properties%2A> . Podtyp projektu může pomocí zařízení pro automatizaci automatizace přidat své vlastnosti do této kolekce. <xref:EnvDTE80.IInternalExtenderProvider>Rozhraní implementované u Agregátoru podtypu hlavního projektu musí nabízet svůj objekt pro `VSHPROPID_BrowseObjectCATID` od <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (odpovídající `itemid` hodnotě [VSITEMID). Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID.

- Konfigurace. Properties: Tato kolekce zpřístupňuje vlastnosti projektu závislé na konfiguraci pro konkrétní konfiguraci (například ladění). Další informace naleznete v tématu <xref:EnvDTE.Configuration>. Podtyp projektu může pomocí zařízení pro automatizaci automatizace přidat své vlastnosti do této kolekce. <xref:EnvDTE80.IInternalExtenderProvider>Rozhraní implementované v Agregátoru podtypu hlavní projekt nabízí svůj objekt pro CATID `VSHPROPID_CfgBrowseObjectCATID` (odpovídající `itemid` hodnotě [VSITEMID. Kořen](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>Rozhraní se používá k rozlišení jednoho objektu pro procházení konfigurace od druhého.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>
