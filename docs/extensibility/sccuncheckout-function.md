---
title: Sccuncheckout – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUncheckout
helpviewer_keywords:
- SccUncheckout function
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa00faf6fb7605af6098952b2fc592276934d2f1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53923215"
---
# <a name="sccuncheckout-function"></a>SccUncheckout – funkce
Tato funkce vrátí zpět předchozí operace rezervace, a tím obnovení obsahu z vybraného souboru nebo souborů do stavu před rezervace. Všechny změny provedené v souboru od rezervace se ztratí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 %{nfiles/  
 [in] Počet souborů podle `lpFileNames` pole.  
  
 lpFileNames  
 [in] Pole úplná místní cesta názvy souborů, pro které chcete vrátit zpět rezervaci.  
  
 fOptions  
 [in] Příkaz příznaky (nepoužívá).  
  
 pvOptions  
 [in] Možností správy zdrojového kódu plug-konkrétní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Zrušení rezervace bylo úspěšné.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není pod správou zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě. Vrátit zpět rezervaci nebyla úspěšná.|  
|SCC_E_NOTCHECKEDOUT|Uživatel nemá soubor rezervován.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|  
|SCC_E_PROJNOTOPEN|Projekt nebyl otevřen ze správy zdrojového kódu.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="remarks"></a>Poznámky  
 Po provedení této operace `SCC_STATUS_CHECKEDOUT` a `SCC_STATUS_MODIFIED` příznaky oba soubory se odstraní pro soubory, na kterých se provedla zrušení rezervace.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)