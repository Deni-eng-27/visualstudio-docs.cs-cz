---
title: Idebugdocumentcontext – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentContext interface
ms.assetid: 665ee08a-5c6a-4ab1-ab93-de376acc9a74
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 998a219e8a58927ca62ec90e6b105586a64bbf2b
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349579"
---
# <a name="idebugdocumentcontext-interface"></a>IDebugDocumentContext – rozhraní
Poskytuje abstraktní reprezentace část dokumentu, který se právě ladí. Tento zápis se skládá z rozsahu pozice znaku pro textové dokumenty.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugDocumentContext` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentContext::GetDocument](../../winscript/reference/idebugdocumentcontext-getdocument.md)|Vrátí dokument, který obsahuje tento kontext.|  
|[IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)|Vytvoří výčet kontexty kód spojený s tímto kontextem dokumentu.|