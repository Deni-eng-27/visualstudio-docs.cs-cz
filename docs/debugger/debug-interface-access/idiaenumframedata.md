---
title: "Idiaenumframedata – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumFrameData interface
ms.assetid: 2ca7fd5a-b2fa-4b3a-9492-0263eafc435b
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1850fd8eab4151dfb24bdc30dafe2e110406c37a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumframedata"></a>IDiaEnumFrameData
Vytvoří výčet různé datové prvky rámce obsažené v datovém zdroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumFrameData : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaEnumFrameData`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiaenumframedata::get__newenum –](../../debugger/debug-interface-access/idiaenumframedata-get-newenum.md)|Načte `IEnumVARIANT Interface` verzi této enumerátor.|  
|[Idiaenumframedata::get_count –](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)|Získá počet elementů datové rámce.|  
|[Idiaenumframedata::Item –](../../debugger/debug-interface-access/idiaenumframedata-item.md)|Načte datový prvek rámce prostřednictvím indexu.|  
|[Idiaenumframedata::Next –](../../debugger/debug-interface-access/idiaenumframedata-next.md)|Načte zadaný počet elementů dat rámce v pořadí výčtu.|  
|[Idiaenumframedata::Skip –](../../debugger/debug-interface-access/idiaenumframedata-skip.md)|Přeskočí zadaný počet rámce datových elementů v posloupnosti výčtu.|  
|[Idiaenumframedata::Reset –](../../debugger/debug-interface-access/idiaenumframedata-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Idiaenumframedata::clone –](../../debugger/debug-interface-access/idiaenumframedata-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[Idiaenumframedata::framebyrva –](../../debugger/debug-interface-access/idiaenumframedata-framebyrva.md)|Vrátí rámeček s relativní virtuální adresy (RVA).|  
|[Idiaenumframedata::framebyva –](../../debugger/debug-interface-access/idiaenumframedata-framebyva.md)|Vrátí rámeček podle virtuální adresy (VA).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat toto rozhraní [idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md) metoda. Podívejte se na příklad podrobnosti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat ( `GetEnumFrameData` funkce) a použít ( `ShowFrameData` funkce) `IDiaEnumFrameData` rozhraní. Najdete v článku [idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) rozhraní příklad `PrintFrameData` funkce.  
  
```C++  
  
      IDiaEnumFrameData* GetEnumFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pUnknown    = NULL;  
    REFIID             iid         = __uuidof(IDiaEnumFrameData);  
    IDiaEnumTables*    pEnumTables = NULL;  
    IDiaTable*         pTable      = NULL;  
    ULONG              celt        = 0;  
  
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
  
void ShowFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pEnumFrameData = GetEnumFrameData(pSession);;  
  
    if (pEnumFrameData != NULL)  
    {  
        IDiaFrameData* pFrameData;  
        ULONG celt = 0;  
  
        while(pEnumFrameData->Next(1, &pFrameData, &celt) == S_OK &&  
              celt == 1)  
        {  
            PrintFrameData(pFrameData);  
            pFrameData->Release();  
        }  
        pEnumFrameData->Release();   
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** Dia2.h  
  
 **Knihovna:** diaguids.lib  
  
 **Knihovny DLL:** msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)