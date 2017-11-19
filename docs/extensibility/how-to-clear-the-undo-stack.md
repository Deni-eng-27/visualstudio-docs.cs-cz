---
title: "Postupy: Vymazat zásobníku vrácení zpět | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a0d79b16c911390322c8ea3c27a0b0f8cd5d15d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-clear-the-undo-stack"></a>Postupy: Vymazat zásobníku vrácení zpět
Následující následující postup vysvětluje, jak vymazat zásobníku vrácení zpět.  
  
### <a name="to-clear-the-undo-stack"></a>Zrušte operace vrácení zpět zásobníku  
  
1.  Zrušte zaškrtnutí políčka použít zásobníku vrácení zpět [IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799) metoda. Následuje příklad tohoto:  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Implementace správy vrácení zpět](../extensibility/how-to-implement-undo-management.md)