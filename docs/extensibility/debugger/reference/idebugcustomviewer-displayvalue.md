---
title: IDebugCustomViewer::D isplayValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 32e444d0d6a30484f708d3001b95e7a71856edd5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80732452"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
Tato metoda je volána k zobrazení zadané hodnoty.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DisplayValue(
   HWND             hwnd,
   DWORD            dwID,
   IUnknown *       pHostServices,
   IDebugProperty3* pDebugProperty);
);
```

```csharp
int DisplayValue(
   IntPtr          hwnd,
   uint            dwID,
   object          pHostServices,
   IDebugProperty3 pDebugProperty
);
```

## <a name="parameters"></a>Parametry
`hwnd`\
pro Nadřazené okno

`dwID`\
pro ID pro vlastní diváky, kteří podporují více než jeden typ.

`pHostServices`\
pro Rezervovaný. Vždy nastavte na hodnotu null.

`pDebugProperty`\
pro Rozhraní, které lze použít k načtení hodnoty, která se má zobrazit.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí `S_OK` . jinak vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Zobrazení je "modální" v tom, že tato metoda vytvoří potřebné okno, zobrazí hodnotu, počká na vstup a zavře okno, před návratem k volajícímu. To znamená, že metoda musí zpracovat všechny aspekty zobrazení hodnoty vlastnosti, od vytvoření okna pro výstup, pro čekání na vstup uživatele pro zničení okna.

 Pro podporu změny hodnoty na daném objektu [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) můžete použít metodu [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) – Pokud hodnotu lze vyjádřit jako řetězec. V opačném případě je nutné vytvořit vlastní rozhraní – výhradně pro vyhodnocení výrazu implementující tuto `DisplayValue` metodu – u stejného objektu, který implementuje `IDebugProperty3` rozhraní. Toto vlastní rozhraní poskytuje metody pro změnu dat libovolné velikosti nebo složitosti.

## <a name="see-also"></a>Viz také
- [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)
