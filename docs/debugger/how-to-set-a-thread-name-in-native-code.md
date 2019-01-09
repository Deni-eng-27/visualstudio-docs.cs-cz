---
title: 'Postupy: Nastavení názvu vlákna v nativním kódu | Dokumentace Microsoftu'
ms.date: 12/17/2018
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], threads
- SetThreadName function
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c85d0968-9f22-4d69-87f4-acca2ae777b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ecc9eb2dc437847786022526265bfcc2942ace88
ms.sourcegitcommit: 73861cd0ea92e50a3be1ad2a0ff0a7b07b057a1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2019
ms.locfileid: "54153651"
---
# <a name="how-to-set-a-thread-name-in-native-code"></a>Postupy: Nastavení názvu vlákna v nativním kódu
Pojmenování vlákna je možné v jakékoli edici sady Visual Studio. Pojmenování vláken je užitečné pro identifikaci vlákna podíl **vlákna** okno při ladění spuštěného procesu. S zřejmou názvem vláken může být také užitečné při ladění a dodatečně prostřednictvím kontroly výpisu při selhání a analýza výkonu zachycuje pomocí různých nástrojů.

## <a name="ways-to-set-a-thread-name"></a>Způsoby nastavení názvu vlákna

Existují dva způsoby, jak nastavení názvu vlákna. První je prostřednictvím [SetThreadDescription](https://docs.microsoft.com/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreaddescription) funkce. Druhou možností je vyvolání konkrétní výjimky, když je k procesu připojen ladicí program sady Visual Studio. Každý přístup má své výhody a upozornění.

Je vhodné poznamenat, že _obě_ přístupů je použít společně, v případě potřeby, protože jsou mechanismy, které fungují nezávisle na sobě navzájem.

### <a name="set-a-thread-name-by-using-setthreaddescription"></a>Nastavení názvu vlákna s použitím `SetThreadDescription`

Výhody:
 * Názvy vláken jsou viditelné při ladění v sadě Visual Studio bez ohledu na to, zda byl připojen ladicí program k procesu v době, která je vyvolána SetThreadDescription.
 * Názvy vláken jsou viditelné při následné ladění načtením výpisu v sadě Visual Studio.
 * Názvy vláken jsou také viditelné při použití jiných nástrojů, jako [WinDbg](https://docs.microsoft.com/windows-hardware/drivers/debugger/debugger-download-tools) ladicího programu a [Analyzátor výkonu Windows](https://docs.microsoft.com/windows-hardware/test/wpt/windows-performance-analyzer) Analyzátor výkonu.

Upozornění:
 * Názvy vláken jsou pouze v sadě Visual Studio 2017 verze 15.6 a vyšší.
 * Pokud soubor výpisu následné chybovému ukončení ladění, názvy vláken viditelné pouze pokud selhání byl vytvořen v systému Windows 10 verze 1607, Windows Server 2016 nebo novější verze systému Windows.
 
*Příklad:*

```C++
#include <windows.h>
#include <processthreadsapi.h>

int main()
{
    HRESULT r;
    r = SetThreadDescription(
        GetCurrentThread(),
        L"ThisIsMyThreadName!"
    );

    return 0;
}
```

### <a name="set-a-thread-name-by-throwing-an-exception"></a>Nastavení názvu vlákna vyvoláním výjimky

Dalším způsobem, jak nastavení názvu vlákna ve svém programu je pro komunikaci název požadovaného vlákno v ladicím programu sady Visual Studio pomocí vyvolání výjimky speciálně nakonfigurován. 

Výhody:
 * Pracuje se všemi verzemi sady Visual Studio.

Upozornění:
 * Funguje jenom v případě, že v době, kdy se používá metodu založenou na výjimku, je připojen ladicí program. 
 * Názvy vláken nastavené pomocí této metody není k dispozici v výpisů paměti nebo nástroje pro analýzu výkonu.
 
*Příklad:*

`SetThreadName` Funkce uvedené níže ukazuje tento přístup na základě výjimky. Mějte na paměti, že název vlákna budou automaticky kopírována do vlákna, tak, aby paměť pro `threadName` parametr, může se vydávat po dokončení `SetThreadName` dokončením volání. 

```C++
//  
// Usage: SetThreadName ((DWORD)-1, "MainThread");  
//  
#include <windows.h>  
const DWORD MS_VC_EXCEPTION = 0x406D1388;  
#pragma pack(push,8)  
typedef struct tagTHREADNAME_INFO  
{  
    DWORD dwType; // Must be 0x1000.  
    LPCSTR szName; // Pointer to name (in user addr space).  
    DWORD dwThreadID; // Thread ID (-1=caller thread).  
    DWORD dwFlags; // Reserved for future use, must be zero.  
 } THREADNAME_INFO;  
#pragma pack(pop)  
void SetThreadName(DWORD dwThreadID, const char* threadName) {  
    THREADNAME_INFO info;  
    info.dwType = 0x1000;  
    info.szName = threadName;  
    info.dwThreadID = dwThreadID;  
    info.dwFlags = 0;  
#pragma warning(push)  
#pragma warning(disable: 6320 6322)  
    __try{  
        RaiseException(MS_VC_EXCEPTION, 0, sizeof(info) / sizeof(ULONG_PTR), (ULONG_PTR*)&info);  
    }  
    __except (EXCEPTION_EXECUTE_HANDLER){  
    }  
#pragma warning(pop)  
}  
```  

## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Postupy: Nastavení názvu vlákna ve spravovaném kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md)
