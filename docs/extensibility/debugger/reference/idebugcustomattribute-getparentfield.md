---
title: IDebugCustomAttribute::GetParentField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomAttribute::GetParentField
helpviewer_keywords: IDebugCustomAttribute::GetParentField
ms.assetid: bcdfdf37-bfcf-4988-a7b8-4c731d0af1b0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 47aba2e8861ff03e01b67370d61c9e7c3685b9a5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcustomattributegetparentfield"></a>IDebugCustomAttribute::GetParentField
Získá pole, ke kterému je připojen vlastních atributů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetParentField(   
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetParentField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppField`  
 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt, který reprezentuje pole, ke kterému je připojen vlastních atributů.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metodu vrácených [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) je objekt, který chcete zjistit, co nadřazený typ pole.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)