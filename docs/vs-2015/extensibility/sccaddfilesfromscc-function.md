---
title: Sccaddfilesfromscc – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d5af748c9180644cae928d1b6db3a3f880b6b286
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200918"
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce přidá seznam souborů ze správy zdrojových kódů aktuálně otevřeném projektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 lpUser  
 [out v] Uživatelské jméno (až SCC_USER_SIZE, včetně ukončovacího znaku null).  
  
 lpAuxProjPath  
 [out v] Pomocné řetězec, který identifikuje projektu (až `SCC_PRJPATH_`velikost, včetně ukončovacího znaku null).  
  
 cFiles  
 [in] Počet souborů, které jsou uvedena v každém `lpFilePaths`.  
  
 lpFilePaths  
 [out v] Pole názvy souborů přidejte do aktuálního projektu.  
  
 lpDestination  
 [in] Cílová cesta kde soubory jsou k zapsání.  
  
 lpComment  
 [in] Komentář, který se má použít pro všechny přidávané soubory.  
  
 pbResults  
 [out v] Pole příznaky, které jsou sady, čímž indikuje úspěšné provedení (nenulovou hodnotu nebo hodnotu TRUE) nebo selhání (nula nebo hodnotu NEPRAVDA) pro každý soubor (velikost pole musí být dlouhý aspoň `cFiles` dlouhý).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Value|Popis|  
|-----------|-----------------|  
|SCC_E_PROJNOTOPEN|Projekt není otevřen.|  
|SCC_E_OPNOTPERFORMED|Připojení není na stejný projekt podle specifikace `lpAuxProjPath.`|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k aktualizaci databáze.|  
|SCC_E_NONSPECIFICERROR|Neznámá chyba|  
|SCC_I_RELOADFILE|Soubor nebo projekt je potřeba znovu načíst.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
