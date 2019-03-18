---
title: IDebugApplicationNode100::QueryIsChildNode | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::QueryIsChildNode
ms.assetid: 4f36f435-0f34-4f9e-bba3-e75285fd7bbb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f620a5545c65683eaafd0ac457621f01e6782dff
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58151099"
---
# <a name="idebugapplicationnode100queryischildnode"></a>IDebugApplicationNode100::QueryIsChildNode
Určuje, zda zadaný dokument patří do jedné z podřízených uzlů tohoto uzlu.  
  
> [!IMPORTANT]
>  [Idebugapplicationnode100 – rozhraní](../../winscript/reference/idebugapplicationnode100-interface.md) je implementováno pomocí PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT QueryIsChildNode(        [in] IDebugDocument* pSearchKey        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `pSearchKey`  
 Klíč hledání.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationNode100 – rozhraní](../../winscript/reference/idebugapplicationnode100-interface.md)