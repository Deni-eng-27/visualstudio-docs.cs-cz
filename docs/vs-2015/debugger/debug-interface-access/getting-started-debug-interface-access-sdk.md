---
title: Začínáme (Debug Interface Access SDK) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 54f83f00ed2e99d1541e15092cb3ee0ce9e08952
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68164174"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Začínáme (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Sada SDK přístup k rozhraní ladění (DIA) poskytuje pokyny a ukázku, která ukazuje, jak používat rozhraní DIA API. Použijte rozhraní a metody v DIA SDK k vývoji vlastních aplikací, které otevřou soubory. pdb a. dbg, a vyhledejte jejich obsah pro symboly, hodnoty, atributy, adresy a další informace o ladění. Tato sada SDK také poskytuje referenční tabulky pro vlastnosti přidružené ke symbolům nalezeným v aplikacích C++.  
  
 Chcete-li nejlépe použít DIA SDK, měli byste být obeznámeni s následujícím:  
  
- Programovací jazyk C++  
  
- Programování COM  
  
- Integrované vývojové prostředí (IDE) sady Visual Studio pro kompilování ukázek  
  
  DIA SDK se obvykle instaluje se sadou Visual Studio a její výchozí umístění je *[jednotka]* \Program Files\Microsoft Visual Studio 9.0 \ DIA SDK. V rámci instalace je msdia90.dll, které implementují DIA SDK, automaticky zaregistrován tak, aby je bylo možné použít `dia2.h` v programu a propojit s `diaguids.lib` .  
  
  Záhlaví: include\dia2.h  
  
  Knihovna: lib\diaguids.lib  
  
  KNIHOVNA DLL: bin\msdia80.dll  
  
  IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Kontroluje základní architekturu DIA.  
  
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Poskytuje podrobné pokyny pro použití rozhraní DIA API k dotazování na soubor. pdb.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k rozhraní ladění SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)
