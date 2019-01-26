---
title: Pseudoproměnné | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Watch window, pseudovariables
- debugging [Visual Studio], pseudovariables
- pseudovariables
ms.assetid: fae84f68-2138-4144-9bd4-c9e271b6182a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f7f5eadd7072a3b250fa117909f4d5b2e9c2868f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925432"
---
# <a name="pseudovariables-in-the-visual-studio-debugger"></a>Pseudoproměnné v ladicím programu sady Visual Studio
Pseudoproměnné jsou podmínky, které slouží k zobrazení určitých informací v okně proměnné nebo **QuickWatch** dialogové okno. Pseudoproměnnou můžete zadat stejným způsobem, zadali byste jako běžné proměnné. Pseudoproměnné nejsou proměnné, ale a nemusí odpovídat názvům proměnných v programu.  
  
## <a name="example"></a>Příklad  
 Předpokládejme, že píšete aplikaci v nativním kódu a chcete zjistit počet popisovačů přidělených v aplikaci. V **Watch** okna, můžete zadat následující pseudoproměnnou **název** sloupce, poté stiskem klávesy ENTER ji vyhodnotit:  
  
`$handles`
  
 V nativním kódu můžete použít pseudoproměnné uvedené v této tabulce:  
  
|Pseudoproměnnou|Funkce|  
|--------------------|--------------|  
|`$err`|Zobrazí poslední chybovou hodnotu nastavenou pomocí funkce SetLastError. Zobrazená hodnota představuje, co by vrátila Funkce GetLastError.<br /><br /> Použití `$err,hr` Chcete-li zobrazit dekódovanou formu této hodnoty. Například, pokud byla poslední chyba 3 `$err,hr` zobrazí `ERROR_PATH_NOT_FOUND : The system cannot find the path specified.`|  
|`$handles`|Zobrazí počet popisovačů přidělených v aplikaci.|  
|`$vframe`|Zobrazí adresu aktuální rámec zásobníku.|  
|`$tid`|Zobrazí identifikátor ID vlákna pro aktuální vlákno.|  
|`$env`|Zobrazí zadaný blok prostředí v prohlížeči řetězce.|  
|`$cmdline`|Zobrazí řetězec příkazového řádku, který spustil program.|  
|`$pid`|Zobrazuje id procesu.|  
|`$` *registername –*<br /><br /> or<br /><br /> `@` *registername –*|Zobrazí obsah registru *registername –*.<br /><br /> Obsah registru za normálních okolností lze zobrazit pouze zadáním názvu registru. Je třeba použít tuto syntaxi se pouze když název registru přetíží název proměnné. Pokud název registru je stejný jako název proměnné v aktuálním oboru, ladicí program interpretuje název jako název proměnné. Právě to `$` *registername –* nebo `@` *registername –* se hodí.|  
|`$clk`|Zobrazí čas v hodinových cyklech.|  
|`$user`|Zobrazí se struktura s informacemi o účtu pro účet, který spouští aplikaci. Z bezpečnostních důvodů nejsou informace heslu zobrazeny.|  
|`$exceptionstack`|Zobrazí trasování zásobníku aktuální výjimky prostředí Windows Runtime. `$ exceptionstack` funguje pouze v aplikacích pro UPW. `$ exceptionstack` není podporováno pro výjimky C++ a SEH|  
|`$ReturnValue`|Zobrazuje hodnotu vrácenou metody rozhraní .NET Framework.|  
  
 V jazyce C# a Visual Basic můžete použít pseudoproměnné uvedené v této tabulce:  
  
|Pseudoproměnnou|Funkce|  
|--------------------|--------------|  
|`$exception`|Zobrazí informace o poslední výjimce. Pokud k žádné výjimce, hodnocení `$exception` zobrazí chybovou zprávu.<br /><br /> V jazyce Visual C#, zakázán Pomocník pro výjimky, `$exception` se automaticky přidá do **lokální** okno, když dojde k výjimce.|  
|`$user`|Zobrazí se struktura s informacemi o účtu pro účet, který spouští aplikaci. Z bezpečnostních důvodů nejsou informace heslu zobrazeny.|  
  
 V jazyce Visual Basic můžete použít pseudoproměnné uvedené v následující tabulce:  
  
|Pseudoproměnnou|Funkce|  
|--------------------|--------------|  
|`$delete` Nebo `$$delete`|Odstraní implicitní proměnné, který byl vytvořen v **okamžité** okna. Syntaxe je `$delete,` *proměnnou* nebo`$delete,` *proměnné*`.`|  
|`$objectids` Nebo `$listobjectids`|Zobrazí všechny aktivní ID objektů jako podřízené položky, z určeného výrazu. Syntaxe je `$objectid,` *výraz* nebo`$listobjectids,` *výraz*`.`|  
|`$` *N* `#`|Zobrazí objekt s ID objektu rovna *N*.|  
|`$dynamic`|Zobrazí zvláštní **dynamického zobrazení** uzlu pro objekt, který implementuje `IDynamicMetaObjectProvider`. rozhraní. Syntaxe je `$dynamic,` *objekt*. Tato funkce se vztahuje pouze na kód, který používá rozhraní .NET Framework verze 4.|  
  
## <a name="see-also"></a>Viz také  
 [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Proměnné Windows](../debugger/debugger-windows.md)