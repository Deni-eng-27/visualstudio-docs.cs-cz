---
title: Pokračování v provádění po výjimce | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e94867d845988b787247c32d32afd35af946972
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85350677"
---
# <a name="continuing-execution-after-an-exception"></a>Pokračování v provádění po výjimce
Pokud ladicí program přeruší provádění z důvodu výjimky, ve výchozím nastavení se zobrazí **Pomocník pro výjimky**. Pokud jste zakázali **pomocníka výjimky** v dialogovém okně **Možnosti** , zobrazí se **Pomocník pro výjimky** (C# nebo Visual Basic) nebo dialogové okno **výjimky** (C++).

 Po zobrazení **pomocníka výjimky** se můžete pokusit opravit problém, který způsobil výjimku.

## <a name="managed-and-native-code"></a>Spravovaný a nativní kód
 Ve spravovaném a nativním kódu můžete pokračovat v provádění ve stejném vlákně po neošetřené výjimce. **Pomocné rutina výjimky** odvíjí zásobník volání do bodu, kde byla vyvolána výjimka.

## <a name="mixed-code"></a>Smíšený kód
 Pokud při ladění smíšeného nativního a spravovaného kódu dojde k neošetřené výjimce, omezení operačního systému zabrání odvinutí zásobníku volání. Pokud se pokusíte převinout zásobník volání pomocí místní nabídky, zobrazí se chybová zpráva s vysvětlením, že ladicí program nemůže provést zpětnou akci před neošetřenou výjimkou při ladění smíšeného kódu.

## <a name="see-also"></a>Viz také

- [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)