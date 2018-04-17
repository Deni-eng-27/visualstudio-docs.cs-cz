---
title: Seznam zásobník volání – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.listcallstack
helpviewer_keywords:
- list call stack command
- Debug.ListCallStack command
ms.assetid: a8b20bf2-81d2-4069-aea8-23e6b15b4347
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3b9a0f9c466325d476c01d4acf9b825193fb175
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="list-call-stack-command"></a>Listovat zásobník volání – příkaz
Zobrazí aktuální zásobníku volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListCallStack [/Count:number] [/ShowTypes:yes|no]  
[/ShowNames:yes|no] [/ShowValues:yes|no] [/ShowModule:yes|no]  
[/ShowLineOffset:yes|no] [/ShowByteOffset:yes|no]  
[/ShowLanguage:yes|no] [/IncludeCallsAcrossThreads:yes|no]  
[/ShowExternalCode:yes|no] [Thread:n] [index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Volitelné. Nastaví aktuální rámec zásobníku a zobrazí žádný výstup.  
  
## <a name="switches"></a>Přepínače  
 Každý přepínač lze vyvolat pomocí jeho dokončení formuláře nebo zkrácené formě.  
  
 / Počet:`number` [nebo] / c:`number`  
 Volitelné. Maximální počet zásobníky volání k zobrazení. Výchozí hodnota neomezená.  
  
 / ShowTypes:`yes` &#124; `no` [nebo] / t:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit typy parametrů. Výchozí hodnota je `yes`.  
  
 / ShowNames:`yes` &#124; `no` [nebo] / n:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit názvy parametrů. Výchozí hodnota je `yes`.  
  
 / ShowValues:`yes` &#124; `no` [nebo] / v:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se mají zobrazovat hodnoty parametrů. Výchozí hodnota je `yes`.  
  
 / ShowModule:`yes` &#124; `no` [nebo] / m:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit na název modulu. Výchozí hodnota je `yes`.  
  
 / ShowLineOffset:`yes` &#124; `no` [nebo] /#:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit posun řádku. Výchozí hodnota je `no`.  
  
 / ShowByteOffset:`yes` &#124; `no` [nebo] / b:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit posun bajtů. Výchozí hodnota je `no`.  
  
 / ShowLanguage:`yes` &#124; `no` [nebo] l:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit jazyk. Výchozí hodnota je `no`.  
  
 / IncludeCallsAcrossThreads:`yes` &#124; `no` [nebo] / i:`yes`&#124;`no`  
 Volitelné. Určuje, jestli zahrnují volání do nebo z jiných vláken. Výchozí hodnota je `no`.  
  
 / ShowExternalCode:`yes`&#124;`no`  
 Volitelné. Určuje, jestli se má zobrazit pouze můj kód pro zásobník volání. Když pouze můj kód je vypnutý, zobrazí se všechny bez uživatelského kódu. Pokud pouze můj kód na, zobrazí se jiný uživatelský kód jako `[external]` ve výstupu zásobník volání.  
  
 Přístup z více vláken:`n`  
 Volitelné. Zobrazí zásobník volání pro přístup z více vláken `n`. Pokud není zadaný žádný přístup z více vláken, zobrazuje zásobník volání pro aktuální vlákno.  
  
## <a name="remarks"></a>Poznámky  
 Změny provedené v přepínači nebo argumenty platí pro budoucí volání tohoto příkazu. Pokud vydáte Debug.ListCallStackby sám sebe, zobrazí se celý zásobník volání. Pokud například zadáte index,  
  
```  
Debug.ListCallStack 2  
```  
  
 aktuální rámec zásobníku bude nastavena na tomto snímku (v tomto případě druhý snímek).  
  
 Je také možné zapsat tento příkaz pomocí jeho předem definovaný alias kb. Například můžete zadat  
  
```  
kb 2  
```  
  
 nastavit aktuální rámec zásobníku na druhý rámečku.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.CallStack /Count:4 /ShowTypes:yes  
```  
  
## <a name="see-also"></a>Viz také  
 [Seznam zpětný překlad – příkaz](../../ide/reference/list-disassembly-command.md)   
 [Listovat vlákna – příkaz](../../ide/reference/list-threads-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)