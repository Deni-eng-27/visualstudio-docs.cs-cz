---
title: Pseudoproměnné | Microsoft Docs
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
ms.openlocfilehash: 6b6856517a680809ccc802c02dc880b6349eadc5
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/17/2019
ms.locfileid: "72535957"
---
# <a name="pseudovariables-in-the-visual-studio-debugger"></a>Pseudoproměnné v ladicím programu sady Visual Studio
Pseudoproměnné jsou výrazy používané k zobrazení určitých informací v okně proměnných nebo v dialogovém okně **QuickWatch** . Pseudoproměnnou můžete zadat stejným způsobem, jako byste zadali normální proměnnou. Pseudoproměnné nejsou proměnné, ale neodpovídají názvům proměnných v programu.

## <a name="example"></a>Příklad
 Předpokládejme, že píšete aplikaci nativního kódu a chcete zobrazit počet popisovačů přidělených ve vaší aplikaci. V okně **kukátko** můžete do sloupce **název** zadat následující pseudoproměnnou a pak ho vyhodnotit stisknutím klávesy ENTER:

`$handles`

 V nativním kódu můžete použít Pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$err`|Zobrazí poslední chybovou hodnotu nastavenou funkcí SetLastError. Zobrazená hodnota představuje to, co by Funkce GetLastError vrátila.<br /><br /> Pro zobrazení Dekódovatelné formy této hodnoty použijte `$err,hr`. Pokud například poslední chyba byla 3, `$err,hr` by se zobrazila `ERROR_PATH_NOT_FOUND : The system cannot find the path specified.`|
|`$handles`|Zobrazuje počet popisovačů přidělených ve vaší aplikaci.|
|`$vframe`|Zobrazí adresu aktuálního rámce zásobníku.|
|`$tid`|Zobrazuje ID vlákna pro aktuální vlákno.|
|`$env`|Zobrazí blok prostředí v prohlížeči řetězců.|
|`$cmdline`|Zobrazí řetězec příkazového řádku, který spustil program.|
|`$pid`|Zobrazí ID procesu.|
|`$` *registru*<br /><br /> or<br /><br /> `@` *registru*|Zobrazí *obsah registru Register.*<br /><br /> V normálním případě lze obsah registru zobrazit pouze zadáním názvu registru. Jedinou dobu, kterou potřebujete použít k použití této syntaxe, je, když název registru převede název proměnné. Pokud je název registru stejný jako název proměnné v aktuálním oboru, ladicí program interpretuje název jako název proměnné. To je v případě, že se `$`*registru* nebo `@`*registru* nachází v praktických případech.|
|`$clk`|Zobrazí čas v časovém cyklu.|
|`$user`|Zobrazí strukturu s informacemi o účtu pro účet, na kterém je aplikace spuštěná. Z bezpečnostních důvodů se nezobrazuje informace o hesle.|
|`$exceptionstack`|Zobrazí trasování zásobníku aktuální výjimky prostředí Windows Runtime. `$ exceptionstack` funguje jenom v aplikacích pro UWP. `$ exceptionstack` se nepodporuje pro C++ výjimky a SEH.|
|`$returnvalue`|Zobrazuje návratovou hodnotu metody .NET.|

 V C# nástroji můžete použít Pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$exception`|Zobrazí informace o poslední výjimce. Pokud nedošlo k žádné výjimce, vyhodnocení `$exception` zobrazí chybovou zprávu.<br /><br /> Pokud je pomocník výjimek zakázán, `$exception` je automaticky přidán do okna **místní** hodnoty, když dojde k výjimce.|
|`$user`|Zobrazí strukturu s informacemi o účtu pro účet, na kterém je aplikace spuštěná. Z bezpečnostních důvodů se nezobrazuje informace o hesle.|
|`$returnvalue`|Zobrazuje návratovou hodnotu metody .NET.|

 V Visual Basic můžete použít Pseudoproměnné uvedené v následující tabulce:

|Pseudoproměnnou|Funkce|
|--------------------|--------------|
|`$exception`|Zobrazí informace o poslední výjimce. Pokud nedošlo k žádné výjimce, vyhodnocení `$exception` zobrazí chybovou zprávu.|
|`$delete` nebo `$$delete`|Odstraní implicitní proměnnou, která byla vytvořena v **příkazovém** okně. Syntaxe je `$delete,` *proměnnou* nebo `$delete,` *proměnnou* `.`|
|`$objectids` nebo `$listobjectids`|Zobrazí všechna aktivní ID objektů jako podřízené objekty určeného výrazu. Syntaxe je `$objectid,` *výraz* nebo *výraz* `$listobjectids,` `.`|
|`$` *N* `#`|Zobrazí objekt s ID objektu větším než *N*.|
|`$dynamic`|Zobrazí speciální uzel **dynamického zobrazení** pro objekt, který implementuje `IDynamicMetaObjectProvider`. Prostředí. Syntaxe je `$dynamic,` *objekt*. Tato funkce se vztahuje pouze na kód, který používá .NET Framework verze 4 nebo novější.|

## <a name="see-also"></a>Viz také
- [Okna Kukátko a Rychlé kukátko](../debugger/watch-and-quickwatch-windows.md)
- [Okna proměnných](../debugger/debugger-windows.md)
