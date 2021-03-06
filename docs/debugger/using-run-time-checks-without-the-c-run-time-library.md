---
title: Použití kontrol za běhu bez běhové knihovny jazyka C | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.runtime
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors, error checks
- CRT, run-time checks
- debugger, native run-time checks
- run-time errors, run-time checks
- run-time checks, /RTC option
- debugging [Visual Studio], run-time routines
ms.assetid: 30ed90f3-9323-4784-80a4-937449eb54f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 029aafa634ba0e6837cdc7d4304d0419420dd912
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72728667"
---
# <a name="using-run-time-checks-without-the-c-run-time-library"></a>Použití kontrol za běhu bez běhové knihovny jazyka C
Pokud propojíte program bez běhové knihovny jazyka C, pomocí **/NODEFAULTLIB**a chcete použít kontroly za běhu, musíte propojit s RunTmChk. lib.

`_RTC_Initialize` Inicializuje program pro kontroly za běhu. Pokud neprovedete propojení s knihovnou run-time jazyka C, je nutné zkontrolovat, zda je program kompilován před voláním pomocí kontroly chyb za běhu `_RTC_Initialize` , a to následujícím způsobem:

```cpp
#ifdef __MSVC_RUNTIME_CHECKS
    _RTC_Initialize();
#endif
```

Pokud neprovedete propojení s knihovnou run-time jazyka C, je nutné také definovat funkci s názvem `_CRT_RTC_INITW` . `_CRT_RTC_INITW` nainstaluje uživatelsky definovanou funkci jako výchozí funkci zasílání zpráv o chybách následujícím způsobem:

```cpp
// C version:
_RTC_error_fnW __cdecl _CRT_RTC_INITW(
        void *res0, void **res1, int res2, int res3, int res4)
{
    // set the error handler.
    return &MyErrorFunc;
}

// C++ version:
extern "C" _RTC_error_fnW __cdecl _CRT_RTC_INITW(
       void *res0, void **res1, int res2, int res3, int res4)
{
    // set the error handler:
    return &MyErrorFunc;
}
```

Po instalaci výchozí funkce zasílání zpráv o chybách můžete pomocí nástroje nainstalovat další funkce zasílání zpráv o chybách `_RTC_SetErrorFuncW` . Další informace najdete v tématu [_RTC_SetErrorFuncW](/cpp/c-runtime-library/reference/rtc-seterrorfuncw).

## <a name="see-also"></a>Viz také
[Postupy: použití nativních kontrol za běhu](../debugger/how-to-use-native-run-time-checks.md)
