---
title: "Idiasession::FindFile – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 99f3d58b444f2bf360c76dcd5f95b03ac50f7e32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
Načte zdrojové soubory podle kompilace a názvu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCompiland`  
 [v] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt reprezentující kompilace má být použit jako kontextu pro hledání. Tento parametr nastavte na `NULL` najít v souborech určených ke kompilaci všechny zdrojové soubory.  
  
 `name`  
 [v] Určuje název zdrojového souboru má být načtena. Tento parametr nastavte na `NULL` pro všechny zdrojové soubory, které mají být načteny.  
  
 `option`  
 [v] Určuje možnosti porovnání použita k hledání názvu. Hodnoty z [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčet může být použito samostatně nebo v kombinaci.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md) načíst objekt, který obsahuje seznam zdrojové soubory.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
  
```C++  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)