---
title: "Začínáme (přístup k rozhraní ladění SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d37843917be3a2668e9a2887f046eaee00600dc8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-debug-interface-access-sdk"></a>Začínáme (Přístup k rozhraní ladění SDK)
Ladění rozhraní přístup (DIA) SDK poskytuje vám s instruktážní dokumentace a ukázky, která ukazuje, jak používat rozhraní API DIA. Použití rozhraní a metody v sadě DIA SDK k vývoji vlastních aplikací, které otevřete soubory PDB a dbg a vyhledat obsah pro symboly, hodnoty, atributy, adresy a další informace o ladění. Tato sada SDK poskytuje referenční tabulky pro vlastnosti přidružené k symboly v aplikací C++ nalezen.  
  
 Nejvhodnější používat DIA SDK, byste měli seznámit s následujícími službami:  
  
-   Programovací jazyk C++  
  
-   Programování COM  
  
-   Visual integrované vývojové prostředí (IDE) Studio kompilaci ukázky  
  
 DIA SDK je obvykle nainstalován pomocí sady Visual Studio a jeho výchozí umístění je *[jednotka]*\Program Files\Microsoft 9.0\DIA Visual Studio SDK. Jako součást instalace, msdia90.dll, která implementuje DIA SDK, automaticky registruje, takže všechno, co musíte udělat pro použití je zahrnout `dia2.h` v programu a odkaz na `diaguids.lib`.  
  
 Záhlaví: include\dia2.h  
  
 Knihovna: lib\diaguids.lib  
  
 Knihovny DLL: bin\msdia80.dll  
  
 IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Zkontroluje Základní architektura DIA.  
  
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Obsahuje podrobné pokyny týkající se používání rozhraní API DIA do souboru PDB dotazu.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k rozhraní ladění SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)