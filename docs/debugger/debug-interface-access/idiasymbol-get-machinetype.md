---
title: Idiasymbol::get_machinetype – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_machineType method
ms.assetid: 30870b10-6f32-45c6-a0d7-020dea707710
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f001450f874969007e5f592824bc1a9d693e1cac
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464118"
---
# <a name="idiasymbolgetmachinetype"></a>IDiaSymbol::get_machineType
Načte typ cíle procesoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_machineType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu z [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) výčet, který určuje cílový typ procesoru.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="see-also"></a>Viz také  
 [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)