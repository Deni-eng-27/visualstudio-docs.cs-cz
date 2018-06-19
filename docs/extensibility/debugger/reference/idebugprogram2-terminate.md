---
title: IDebugProgram2::Terminate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5eb14280947ff93a4a0c2ab6d2cf025037fc06aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115834"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
Ukončí program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je to možné program bude ukončen a uvolněna z procesu; modul ladění (DE), jinak hodnota provede všechny nezbytné čištění.  
  
 Tato metoda nebo [ukončit](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) metoda je volána metodou integrovaného vývojového prostředí, obvykle v reakci na uživatele zastavení všech ladění. Implementace této metody by v ideálním případě ukončit programu v rámci procesu. Pokud to není možné, DE by měl program bránit ve spouštění všechny další v tomto procesu (a proveďte všechny nezbytné vyčištění). Pokud `IDebugProcess2::Terminate` byla volána metoda pomocí rozhraní IDE, celý proces bude ukončeno po nějaké době zopakovat `IDebugProgram2::Terminate` metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Ukončení](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)