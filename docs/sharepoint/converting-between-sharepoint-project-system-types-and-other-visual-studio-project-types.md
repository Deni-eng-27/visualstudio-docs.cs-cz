---
title: "Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint project service
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 837907172d4e093dec231e6b21b92da050dcbd19
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types"></a>Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio
  V některých případech může mít objekt v systému projektu služby SharePoint a chcete používat funkce odpovídající objektu v sadě Visual Studio automatizace objektový model nebo integrace objektový model, nebo naopak. V těchto případech můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> metoda projektu služby SharePoint převést objekt na jiný objekt modelu.  
  
 Například můžete mít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu, ale chcete použít metody, které jsou dostupné jenom na <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> objektu. V takovém případě můžete použít <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> k <xref:EnvDTE.Project> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>.  
  
 Další informace o sadě Visual Studio automatizace objektový model a model objektu integrace sady Visual Studio najdete v tématu [přehled programovací Model z rozšíření nástrojů SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md).  
  
## <a name="types-of-conversions"></a>Převody typů  
 Následující tabulka uvádí typy, které tuto metodu můžete přepínat mezi systému projektu služby SharePoint a jinými modely objekt sady Visual Studio.  
  
|Typ systému projektu služby SharePoint|Odpovídající typy v objektové modely automatizace a integrace|  
|------------------------------------|-------------------------------------------------------------------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> or<br /><br /> Žádné rozhraní v sadě Visual Studio integrace objektový model, který je implementováno modulem základní objekt COM pro projekt. Tato rozhraní zahrnují <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> (nebo odvozené rozhraní), a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>. Seznam hlavních rozhraní, které implementují projekty najdete v tématu [základní součásti služby projektu modelu](/visualstudio/extensibility/internals/project-model-core-components).|  
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> or<br /><br /> A<xref:System.UInt32> hodnotu (také nazývané VSITEMID), který identifikuje člena v projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> který ji obsahuje. Tato hodnota může být předán *itemid* parametr některých <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> metody.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> způsobů, jak převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> do objektu <xref:EnvDTE.Project>.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/CSharp/spprojectserviceaddin/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/VisualBasic/spprojectserviceaddin/connect.vb#2)]  
  
 Tento příklad vyžaduje:  
  
-   Rozšíření systému projektu služby SharePoint, který obsahuje odkaz na sestavení EnvDTE.dll. Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).  
  
-   Kód, který registruje `projectService_ProjectAdded` metodu ke zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> události <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> objektu. Příklad, naleznete v části [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
## <a name="see-also"></a>Viz také  
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)   
 [Postupy: načtení služby projektu SharePoint](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [Přehled modelu programování rozšíření nástrojů služby SharePoint](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  