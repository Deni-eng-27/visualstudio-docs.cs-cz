---
title: Funkce SccBeginBatch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5350484294d02356301839e38b97bea1d40ec27c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138233"
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch – funkce
Tato funkce spustí batch posloupnost operací se zdrojovým ovládacího prvku. [SccEndBatch](../extensibility/sccendbatch-function.md) bude volána k ukončení dávky. Tyto dávek nelze vnořit.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dávkové operace úspěšně začalo.|  
|SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Zdroj ovládacího prvku dávky se používá k provedení stejné operace napříč více projektů nebo více kontextů. K vyloučení dialogová okna redundantní projekt z činnost koncového uživatele během dávkové operace můžete použít dávky. `SccBeginBatch` Funkce a [SccEndBatch](../extensibility/sccendbatch-function.md) se používají jako dvojice funkce označující začátek a konec operace. Nemůže být vnořena. `SccBeginBatch` Nastaví příznak označující, že dávkové operace probíhá.  
  
 Během dávkové operace je platná, modul plug-in zdrojového kódu by měla poskytnout maximálně jeden dialogové okno pro všechny otázky, které uživateli a použít odpověď z toto okno zobrazené na všechny následné operace.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)