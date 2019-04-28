---
title: Správa vrátit zpět a znovu pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: adf6a2405ae3d3408f9cf04199ba05dff9232326
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62856426"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>Správa vrácení zpět a znovu pomocí starší verze rozhraní API
Editory musí podporovat operace vrácení zpět, které umožňují uživateli obrátit jejich poslední změny při jejich upravit kód. Většina editory implementovaná v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] může mít podpora pro vracení zpět automaticky poskytuje integrované vývojové prostředí (IDE).

## <a name="in-this-section"></a>V tomto oddílu
- [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md) poskytuje možnost vrácení zpět pro editory s jedním nebo více zobrazení.

- [Postupy: Vymazat zásobník vrácení zpátky](../extensibility/how-to-clear-the-undo-stack.md) popisuje, jak vymazat zásobník akcí zpět.

- [Postupy: Použijte správu propojená operace vrácení zpět](../extensibility/how-to-use-linked-undo-management.md) Incorporates propojené řízení zpět do editoru.

## <a name="reference"></a>Odkaz
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> Poskytuje správu vrácení zpět pro editor, který podporuje několik zobrazení.
