---
title: IDebugArrayObject2::GetBaseIndices | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetBaseIndices
- IDebugArrayObject2::GetBaseIndices
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4673142d0b9866e36b7a53471406f1808e292aea
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673155"
---
# <a name="idebugarrayobject2getbaseindices"></a>IDebugArrayObject2::GetBaseIndices
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugArrayObject2::GetBaseIndices](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject2-getbaseindices).  
  
Získá základní indexy (dolní meze) pro každý index zadaný počet dimenzí v poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetBaseIndices (  
   DWORD  dwRank,  
   DWORD* dwIndices  
);  
```  
  
```csharp  
int GetBaseIndices (  
   uint       dwRank,  
   out uint[] dwIndices  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwRank`  
 [in] Počet rozměrů (pořadí) pole.  
  
 `dwIndices`  
 [out] Základní indexy (dolní meze) pro pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jako příklad vrátí tato funkce '5' pro pole vytvořené pomocí následujícího kódu jazyka C#:  
  
```  
int[] lengths = { 12 };  
int[] lowerbounds = { 5 };  
Array.CreateInstance(typeof(int), lengths, lowerbounds);  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)

