---
title: IDebugExtendedField::IsClosedType | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a1cf28e8391a1dd37949c042bd7d58d9c8b7da06
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148977"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje, zda pole představuje uzavřený typ.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je pole uzavřený typ, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
