---
title: Idiasymbol::get_frontendmajor – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMajor method
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 67d6a614ebac95809050a9f4ceb8201e7d76ee36
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetfrontendmajor"></a>IDiaSymbol::get_frontEndMajor
Načte front-endu hlavní číslo verze.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_frontEndMajor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí front-endu hlavní číslo verze. V části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Kompilátor se obvykle skládá ze dvou primárních prvků: front-endu (Analyzátor), který zpracovává analýzu zdrojový kód do formuláře zprostředkující, a back-end (generátor kódu), který převádí zprostředkující formuláře do sestavení. Je běžné pro front-endu má jinou verzi než back-end.  
  
 Front-end nebo back-end číslo verze se skládá ze tří částí: \<hlavní >.\< méně závažné >. \<sestavení >, kde \<hlavní > je hlavní číslo verze, \<menší > je číslo podverze a \<sestavení > je číslo sestavení. Například 13.10.3077.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)