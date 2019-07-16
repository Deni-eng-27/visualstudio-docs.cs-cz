---
title: Idiadatasource::opensession – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4bec5507d15374e6e88afd4567d4b0fec9ca6cb7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198603"
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Otevře relaci pro dotazování na symboly.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppSession  
 [out] Vrátí [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt představující otevřít relaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Value|Popis|  
|-----------|-----------------|  
|E_UNEXPECTED, JE-|[Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md) objekt nebyl inicializován dříve se zdrojem symboly.|  
|E_INVALIDARG|Neplatný `ppSession` parametru.|  
|E_OUTOFMEMORY|Nedostatek paměti k otevření relace.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se otevře [idiasession –](../../debugger/debug-interface-access/idiasession.md) objekt pro zdroj dat.  
  
 `IDiaSession` objekty implementovat dotazy do zdroje dat. Relace slouží ke správě více adresních prostorů pro každou sadu symboly ladění. Pokud je soubor .exe nebo .dll popsal symboly zdroje dat aktivní více adresy rozsahů adres (například, protože více procesů byl načten) a pak jednu relaci pro každý rozsah adres by měl sloužit.  
  
## <a name="example"></a>Příklad  
  
```cpp#  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)
