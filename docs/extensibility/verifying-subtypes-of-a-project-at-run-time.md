---
title: Ověření podtypů projektu za běhu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 78814ae3b5b25a2e5bc85f55217d6b695f634a84
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680240"
---
# <a name="verify-subtypes-of-a-project-at-run-time"></a>Ověření podtypů projektu za běhu
VSPackage, která závisí na podtyp vlastní projekt by měl obsahovat logiku k vyhledání, která podtypu tak, aby se nemusí zdařit řádně Pokud Podtyp není k dispozici. Následující postup ukazuje, jak ověřit přítomnost zadaným podtypem.

### <a name="to-verify-the-presence-of-a-subtype"></a>Chcete-li ověřit přítomnost podtyp

1.  Získat hierarchii projektu z projektu a řešení objektů jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu přidáním následujícího kódu do vašeho balíčku VSPackage.

    ```csharp
    EnvDTE.DTE dte;
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));

    EnvDTE.Project project;
    project = dte.Solution.Projects.Item(1);

    IVsSolution solution;
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));

    IVsHierarchy hierarchy;
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);

    ```

2.  Přetypování hierarchii <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> rozhraní.

    ```csharp
    IVsAggregatableProjectCorrected AP;
    AP = hierarchy as IVsAggregatableProjectCorrected;

    ```

3.  Získání seznamu identifikátorů GUID typu projektu vyvoláním <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>.

    ```csharp
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();

    ```

4.  Identifikátor GUID zadaným podtypem najdete v seznamu.

    ```csharp
    // Replace the string "MyGUID" with the GUID of the subtype.
    string guidMySubtype = "MyGUID";
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)
    {
        // The specified subtype is present.
    }
    ```

## <a name="see-also"></a>Viz také:
- [Podtypy projektů](../extensibility/internals/project-subtypes.md)
- [Návrh podtypů projektů](../extensibility/internals/project-subtypes-design.md)
- [Vlastnosti a metody rozšířené prostřednictvím podtypů projektů](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)