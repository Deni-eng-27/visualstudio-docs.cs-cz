---
title: IDebugDocumentPositionOffset2::GetRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c86b97fd2437f19e280d9cf9e81454cceee9e47f
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199181"
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
Načte rozsah pro aktuální pozice v dokumentu.

## <a name="syntax"></a>Syntaxe

```cpp
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

## <a name="parameters"></a>Parametry
`pdwBegOffset`\
[out v] Posun počáteční pozice v rozsahu. Tento parametr nastavte na hodnotu null, pokud tyto informace není potřeba.

`pdwEndOffset`\
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

## <a name="see-also"></a>Viz také:
- [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)
- [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)