---
title: Scchistory – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0d8ea9367d364f0374d08423c2acf892fe3ddb7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996256"
---
# <a name="scchistory-function"></a>SccHistory – funkce
Tato funkce zobrazí historie zadané soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvContext`  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 `hWnd`  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 `nFiles`  
 [in] Počet souborů podle `lpFileName` pole.  
  
 `lpFileName`  
 [in] Pole plně kvalifikované názvy souborů.  
  
 `fOptions`  
 [in] Příkaz příznaky (aktuálně nepoužívá).  
  
 `pvOptions`  
 [in] Možností správy zdrojového kódu plug-konkrétní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Historie verzí byl úspěšně získán.|  
|SCC_I_RELOADFILE|Systém správy zdrojového kódu ve skutečnosti změny souboru na disku při načítání historie (například tím, že získáme starou verzi), takže rozhraní IDE byste znovu načíst tento soubor.|  
|SCC_E_FILENOTCONTROLLED|Soubor není pod správou zdrojových kódů.|  
|SCC_E_OPNOTSUPPORTED|Systém správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize. Doporučuje se zkuste to znovu.|  
|SCC_E_PROJNOTOPEN|Projekt nebyl otevřen.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě. Historie souborů nebylo možné získat.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in správy zdrojového kódu může zobrazit svůj vlastní dialogové okno k zobrazení historie každého souboru pomocí `hWnd` jako nadřazeného okna. Můžete také volitelné textový výstup zpětného volání funkce předány [sccopenproject –](../extensibility/sccopenproject-function.md) lze použít, pokud je podporována.  
  
 Všimněte si, že za určitých okolností, soubor zkoumají může změnit během provádění tohoto volání. Například [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] historie příkaz umožňuje uživateli příležitost získat původní verzi souboru. V takovém případě se řídí zdroj modulu plug-in vrátí `SCC_I_RELOAD` upozornit rozhraní IDE, že je nutné znovu načíst soubor.  
  
> [!NOTE]
>  Pokud modul plug-in správy zdrojového kódu nepodporuje tuto funkci pro celou řadu soubory, lze zobrazit pouze historie souborů pro první soubor.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)