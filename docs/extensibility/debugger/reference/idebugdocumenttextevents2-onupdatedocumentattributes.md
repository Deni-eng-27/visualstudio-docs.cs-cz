---
title: IDebugDocumentTextEvents2::onUpdateDocumentAttributes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentTextEvents2::OnUpdateDocumentAttributes
helpviewer_keywords: IDebugDocumentTextEvents2::onUpdateDocumentAttributes
ms.assetid: 31b7d151-9ce2-438e-b405-f8cc46b9f537
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5f0b64821199272a853be611c06ab30747edcf0a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumenttextevents2onupdatedocumentattributes"></a>IDebugDocumentTextEvents2::onUpdateDocumentAttributes
Upozorní příjemce události, že byly aktualizovány atributy dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT onUpdateDocumentAttributes(   
   TEXT_DOC_ATTR_2 textdocattr  
);  
```  
  
```csharp  
int onUpdateDocumentAttributes(   
   enum_TEXT_DOC_ATTR_2 textdocattr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `textdocattr`  
 [v] Kombinace příznaků z [TEXT_DOC_ATTR_2](../../../extensibility/debugger/reference/text-doc-attr-2.md) výčet, který určuje aktualizované atributy dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT_DOC_ATTR_2](../../../extensibility/debugger/reference/text-doc-attr-2.md)