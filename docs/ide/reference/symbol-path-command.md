---
title: "Symbolů cesta příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d446779e4f84bf19e965393f9fa1142c7e4e166a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="symbol-path-command"></a>Cesta k symbolu – příkaz
Nastaví seznam adresářů v ladicím programu pro vyhledávání symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Arguments  
 `pathname`  
 Volitelné. Středníkem oddělené seznamu cest v ladicím programu pro vyhledávání symbolů.  
  
## <a name="remarks"></a>Poznámky  
 Pokud žádné `pathname` je zadán příkaz uvádí aktuální symbol cesty.  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá do seznamu adresářů symbol dvě cesty.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazuje středníky oddělený seznam aktuální symbol cesty.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)