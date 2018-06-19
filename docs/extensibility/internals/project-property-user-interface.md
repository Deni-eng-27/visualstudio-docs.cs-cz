---
title: Vlastnost uživatelské rozhraní projektu | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 788107666f8103a77753b93fa7c1febc73f9b97f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132424"
---
# <a name="project-property-user-interface"></a>Projekt vlastnost uživatelské rozhraní
Podtyp projektu můžete použít položky v projektu **stránky vlastností** dialogové okno jsou poskytnuté základní projekt skrýt nebo nastavit ovládací prvky určené jen pro čtení a celé stránky dodávaný nebo přidat stránek specifických pro dílčí projekt na **Stránky vlastností** dialogové okno.

## <a name="extending-the-project-property-dialog-box"></a>Rozšíření dialogové okno vlastností projektu
 Podtyp projektu implementuje Extender automatizace a objektů procházet konfigurace projektu. Tyto Extender implementovat <xref:EnvDTE.IFilterProperties> rozhraní, chcete-li konkrétní vlastnosti, skrytá nebo jen pro čtení. **Stránky vlastností** dialogové okno základní projektu, implementované základní projekt ctí filtrování provádí Extender automatizace.

 Proces rozšíření **vlastnost projektu** dialogové okno je uvedeno níže:

-   Základní projekt načte Extender z projektu dílčí implementací <xref:EnvDTE80.IInternalExtenderProvider> rozhraní. Toto rozhraní implementovat procházet, projektu automatizace a objekty procházet konfigurace projektu všechny základní projektu.

-   Implementace <xref:EnvDTE80.IInternalExtenderProvider> pro objekt procházet projektu a objekt automatizace projektu delegovat na <xref:EnvDTE80.IInternalExtenderProvider> implementace agregátoru dílčí projektu (to znamená, že `QueryInterface` pro <xref:EnvDTE80.IInternalExtenderProvider> na <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt projektu).

-   Objekt konfigurace procházet základní projekt také implementuje <xref:EnvDTE80.IInternalExtenderProvider> k přímo propojit v rozšiřujícího objektu automatizace z objektu konfigurace dílčí projektu. Deleguje jeho implementace <xref:EnvDTE80.IInternalExtenderProvider> rozhraní implementované agregátoru dílčí projektu.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>, implementované procházet objekt konfigurace projekt, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>, také implementované procházet objekt konfigurace projekt, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> objektu.

-   Podtyp projektu můžete určit příslušné CATIDs pro různé objekty rozšiřitelná základní projektu za běhu načtením následující <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> hodnoty:

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

Pokud chcete zjistit CATIDs pro rozsah projektu, dílčí projektu načte výše uvedené vlastnosti pro [VSITEMID. Kořenové](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>) z `VSITEMID typedef`. Podtyp projektu může také chcete určit, které **stránky vlastností** stránek dialogového okna se zobrazí projektu, závislé i konfiguraci nezávislé. Některé podtypy projektu možná muset odebrat předdefinované stránky a přidejte projekt dílčí konkrétní stránky. Chcete-li povolit toto volání projektu klienta spravovaného <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> metodu pro následující vlastnosti:

-   `VSHPROPID_PropertyPagesCLSIDList` – seznam oddělený středníkem CLSID stránky vlastností konfigurace nezávislé.

-   `VSHPROPID_CfgPropertyPagesCLSIDList —` seznam CLSID stránky závislá na konfiguraci vlastností oddělených středníky.

Protože projekt podtypu agregace <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu, ho můžete přepsat definici tyto vlastnosti určit, které **stránky vlastností** dialogová okna se zobrazí. Podtyp projektu můžete načíst tyto vlastnosti ze základní vnitřní projektu a pak přidat nebo odebrat CLSID podle potřeby.

Nové stránky vlastností přidal podtypem projektu jsou předávány objekt procházet konfigurace projektu ze základního projektu implementace. Tento objekt procházet konfigurace projektu podporuje Extender automatizace. Další informace o AutomationExtenders najdete v tématu [implementace a automatizace Extender pomocí](http://msdn.microsoft.com/Library/0d5c218c-f412-4b28-ab0c-33a611f62356). Stránky vlastností implementované volání dílčí projektu <xref:EnvDTE.Project.Extender%2A> načíst vlastní projektu dílčí konfigurace procházet objekt, který rozšiřuje objekt konfigurace procházet základní projektu.

## <a name="see-also"></a>Viz také

- <xref:EnvDTE.IFilterProperties>
- [Dialogové okno stránky vlastností](http://msdn.microsoft.com/en-us/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)