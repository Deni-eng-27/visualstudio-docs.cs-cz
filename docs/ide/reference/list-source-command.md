---
title: "Seznam zdroj – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2f94f7bea2f4742fa975948d838e0cb01ce5e11e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="list-source-command"></a>Listovat zdroj – příkaz
Zobrazí zadané řádků zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Přepínače  
 / Počet:`number`  
 Volitelné. Určuje počet řádků určených k zobrazení.  
  
 / Aktuální  
 Volitelné. Zobrazuje aktuálního řádku.  
  
 Nebo souborů:`filename`  
 Volitelné. Cesta souboru, který se zobrazí. Pokud není zadaný žádný název souboru, příkaz zobrazí zdrojový kód pro řádek aktuální příkaz.  
  
 / Řádku:`number`  
 Volitelné. Zobrazuje číslo konkrétní řádku.  
  
 / ShowLineNumbers:`yes|no`  
 Volitelné. Určuje, jestli se mají zobrazovat čísla řádků.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Tento příklad uvádí zdrojového kódu z řádku 4 souboru Form1.vb, s čísla řádků, které jsou viditelné.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)