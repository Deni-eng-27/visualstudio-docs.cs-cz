---
title: Idiasymbol::get_backendmajor – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_backEndMajor method
ms.assetid: 900a05dd-c29b-44ad-b46b-f43bda819a66
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: db75ecde0979f6926d5336b4c06d19ead3f86898
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54772182"
---
# <a name="idiasymbolgetbackendmajor"></a>IDiaSymbol::get_backEndMajor
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte back-end hlavní číslo verze kompilátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_backEndMajor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí číslo hlavní verze back-end. Viz poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Kompilátor se obvykle skládá z dvou základní prvky: front-endu (Analyzátor), která zpracovává analýzu zdrojového kódu do zprostředkující formuláře, a back-endu (generátor kódu), který převádí zprostředkující formuláře do sestavení. Není, front-endu mít jinou verzi než back-endu.  
  
 Front-end nebo back-endu číslo verze se skládá ze tří částí: \<hlavní >.\< podverze >. \<sestavení >, kde \<hlavní > je číslo hlavní verze \<podverze > je číslo podverze a \<sestavení > je číslo sestavení. Například 13.10.3077.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
