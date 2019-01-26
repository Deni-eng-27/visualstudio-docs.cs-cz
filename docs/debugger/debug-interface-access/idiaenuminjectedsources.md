---
title: Idiaenuminjectedsources – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources interface
ms.assetid: f97e2392-22e1-48da-b7ce-ad94c8b684b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7482481c2a57127c89e6313cf4dace855aabb18f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55039784"
---
# <a name="idiaenuminjectedsources"></a>IDiaEnumInjectedSources
Zobrazení výčtu různých vloženého zdroje obsažené ve zdroji dat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumInjectedSources : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaEnumInjectedSources`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaEnumInjectedSources::get__NewEnum](../../debugger/debug-interface-access/idiaenuminjectedsources-get-newenum.md)|Načte [rozhraní IEnumVARIANT](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant) verzi výčet.|  
|[IDiaEnumInjectedSources::get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md)|Získá počet vloženého zdroje.|  
|[IDiaEnumInjectedSources::Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)|Načte vložený zdroj pomocí indexu.|  
|[IDiaEnumInjectedSources::Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)|Načte zadaný počet vloženého zdroje v pořadí výčtu.|  
|[IDiaEnumInjectedSources::Skip](../../debugger/debug-interface-access/idiaenuminjectedsources-skip.md)|Vynechá zadaný počet vloženého zdroje v sekvenci výčtu.|  
|[IDiaEnumInjectedSources::Reset](../../debugger/debug-interface-access/idiaenuminjectedsources-reset.md)|Návrat na začátek sekvence výčtu.|  
|[IDiaEnumInjectedSources::Clone](../../debugger/debug-interface-access/idiaenuminjectedsources-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je získán voláním [idiasession::findinjectedsource –](../../debugger/debug-interface-access/idiasession-findinjectedsource.md) metodu s názvem konkrétní zdrojového souboru nebo pomocí volání [idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md) metoda s identifikátorem GUID `IDiaEnumInjectedSources` rozhraní.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat ( `GetEnumInjectedSources` funkce) a použití ( `DumpAllInjectedSources` funkce) `IDiaEnumInjectedSources` rozhraní. Najdete v článku [idiapropertystorage –](../../debugger/debug-interface-access/idiapropertystorage.md) rozhraní pro implementaci `PrintPropertyStorage` funkce. Alternativní výstup, najdete v článku [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) rozhraní.  
  
```C++  
  
IDiaEnumInjectedSources* GetEnumInjectedSources(IDiaSession *pSession)  
{  
    IDiaEnumInjectedSources* pUnknown    = NULL;  
    REFIID                   iid         = __uuidof(IDiaEnumInjectedSources);  
    IDiaEnumTables*          pEnumTables = NULL;  
    IDiaTable*               pTable      = NULL;  
    ULONG                    celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
  
void DumpAllInjectedSources( IDiaSession* pSession)  
{  
    IDiaEnumInjectedSources* pEnumInjSources;  
  
    pEnumInjSources = GetEnumInjectedSources(pSession);  
    if (pEnumInjSources != NULL)  
    {  
        IDiaInjectedSource* pInjSource;  
        ULONG celt = 0;  
  
        while(pEnumInjSources->Next(1, &pInjSource, &celt) == S_OK &&  
              celt == 1)  
        {  
            IDiaPropertyStorage *pPropertyStorage;  
            if (pInjSource->QueryInterface(__uuidof(IDiaPropertyStorage),  
                                           (void **)&pPropertyStorage) == S_OK)  
            {  
                PrintPropertyStorage(pPropertyStorage);  
                pPropertyStorage->Release();  
            }  
            pInjSource->Release();  
        }  
        pEnumInjSources->Release();  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::findinjectedsource –](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)   
 [Idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)