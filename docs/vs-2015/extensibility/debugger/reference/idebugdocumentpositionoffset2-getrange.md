---
title: IDebugDocumentPositionOffset2::GetRange | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a1cfef2ef48439f6111cf2ecf1cf33dcc4ab39e0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49234634"
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte rozsah pro aktuální pozice v dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetRange(  
   DWORD* pdwBegOffset,  
   DWORD* pdwEndOffset  
);  
```  
  
```csharp  
public int GetRange(  
   ref uint pdwBegOffset,  
   ref uint pdwEndOffset  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwBegOffset`  
 [out v] Posun počáteční pozice v rozsahu. Tento parametr nastavte na hodnotu null, pokud tyto informace není potřeba.  
  
 `pdwEndOffset`  
 [out v] Posun koncová pozice rozsahu. Tento parametr nastavte na hodnotu null, pokud tyto informace není potřeba.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Rozsah zadaný v dokumentu umístění pro zarážku umístění používá ladicí stroj (DE) pro hledání dopředu příkaz, který ve skutečnosti přispívá kódu. Zvažte například následující kód:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Řádek 5 přispívá k laděnému programu žádný kód. Pokud ladicí program, který nastaví zarážku na řádku 5 požaduje DE budou prohledány určité doby pro první řádek, jež přispívají kód, ladicí program zadáte rozsah, který obsahuje další Release candidate řádky, kde může být správně umístit zarážky. DE by pak hledá směrem dopředu pomocí tyto řádky až do nalezení řádek, který by mohl přijmout zarážku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)   
 [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)

