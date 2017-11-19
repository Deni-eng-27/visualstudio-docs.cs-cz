---
title: "Správa vrátit zpět a znovu proveďte pomocí starší verze rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 41672845d318707512472f556753f429661d008c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>Správa zpět a znovu pomocí starší verze rozhraní API
Editory musí podporovat operace vrácení zpět, které uživatelům reverse jejich poslední změny při jejich upravit kód. Většina editory implementována v části [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] může mít podporu vrácení zpět automaticky poskytuje integrované vývojové prostředí (IDE).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Implementace správy vrácení zpět](../extensibility/how-to-implement-undo-management.md)  
 Poskytuje možnost vrácení zpět pro editory s jedním nebo více zobrazení.  
  
 [Postupy: Vymazat zásobníku vrácení zpět](../extensibility/how-to-clear-the-undo-stack.md)  
 Popisuje, jak vymazat zásobníku vrácení zpět.  
  
 [Postupy: použití modulu Správa propojená operace vrácení zpět](../extensibility/how-to-use-linked-undo-management.md)  
 Propojená operace vrácení zpět správu zapadá do vaší editor.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 Poskytuje správu vrácení zpět pro editor, který podporuje více zobrazení.  
  
## <a name="related-sections"></a>Související oddíly