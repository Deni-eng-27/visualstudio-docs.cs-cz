---
title: Funkce SccProperties | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f4e8452465873cb66883abd347406d17b469e90a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68200004"
---
# <a name="sccproperties-function"></a>SccProperties – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce zobrazuje vlastnosti správy zdrojového kódu pro soubor nebo projekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccProperties (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 pro Struktura kontextu modulu plug-in správy zdrojových kódů.  
  
 hWnd  
 pro Popisovač okna rozhraní IDE, který modul plug-in správy zdrojového kódu může použít jako nadřazený pro všechna dialogová okna, která poskytuje.  
  
 lpFileName  
 pro Plně kvalifikovaný název cesty souboru nebo projektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Při implementaci modulu plug-in správy zdrojových kódů této funkce se očekává, že se vrátí jedna z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Vlastnosti se úspěšně zobrazily.|  
|SCC_I_RELOADFILE|Systém správy verzí změnil vlastnosti souboru, takže IDE by měl tento soubor znovu načíst.|  
|SCC_E_PROJNOTOPEN|Zadaný projekt nebyl otevřen ve správě zdrojového kódu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k zobrazení vlastností tohoto souboru nebo projektu.|  
|SCC_E_FILENOTCONTROLLED|Zadaný soubor nebo projekt není pod správou zdrojových kódů.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k neznámé nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in správy zdrojových kódů zobrazuje vlastnosti ve vlastním dialogovém okně.  
  
 Vlastnosti jsou definovány modulem plug-in správy zdrojových kódů a mohou se lišit od modulu plug-in s modulem plug-in. Pokud modul plug-in umožní uživateli změnit vlastnosti správy zdrojového kódu souboru, měl by se vrátit `SCC_I_RELOAD` k signalizaci rozhraní IDE, že je nutné znovu načíst soubor nebo projekt.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
