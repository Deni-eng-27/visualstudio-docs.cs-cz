---
title: Podpora průvodce pro vnořené projekty | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6fd9871e794c2968bab3effce0717ea1cae508eb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62907538"
---
# <a name="wizard-support-for-nested-projects"></a>Podpora průvodce pro vnořené projekty
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Rozhraní IDE spustí dvě průvodců, které implementují nadřazený projekt pro vnořené projekty: **nový projekt** průvodce a **přidat položku** průvodce.  
  
 Pokud uživatel spustí **nový projekt** průvodce tak, že vyberete **přidat projekt** a kliknete na **nový projekt** v nabídce Soubor nebo tak, že vyberete **přidat** a kliknutím pravým tlačítkem **nový projekt** v Průzkumníku řešení integrovaném vývojovém prostředí běží **AddProject** příkazu a provádění nadřazený projekt **AddProject**příkaz vrátí buď soubor šablony projektu nebo soubor průvodce (.vsz), který obsahuje sadu kontextové parametry.  
  
 Obdobně nadřazený projekt provádění **AddItem** průvodců vrátí souboru, který má jinou sadu kontextové parametry.  
  
 Další informace o Průvodci, najdete v tématu [průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md), [kontextových parametrů](../../extensibility/internals/context-parameters.md) a [registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Vnoření projektů](../../extensibility/internals/nesting-projects.md)
