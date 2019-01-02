---
title: Sccdirqueryinfo – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f710dfed6a6f5225fd74f828077eb228124714c5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956800"
---
# <a name="sccdirqueryinfo-function"></a>Sccdirqueryinfo – funkce
Tato funkce zkontroluje seznam plně kvalifikovaných adresářů pro jejich aktuální stav.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
### <a name="parameters"></a>Parametry  
 pContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 nDirs  
 [in] Počet adresářů vybraných bude Dotazováno.  
  
 lpDirNames  
 [in] Pole plně kvalifikovanou cestou adresářů, aby se dalo dotazovat.  
  
 lpStatus  
 [out v] Struktury pole vrátit příznaky stavu modulu plug-in správy zdrojového kódu (viz [Directory stavový kód](../extensibility/directory-status-code-enumerator.md) podrobnosti).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dotaz byl úspěšný.|  
|SCC_E_OPNOTSUPPORTED|Systém správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|K nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Funkce naplní návratový pole s bitovou maskou bitů z `SCC_DIRSTATUS` řady (naleznete v tématu [Directory stavový kód](../extensibility/directory-status-code-enumerator.md)), jeden záznam pro každý adresář zadaný. Pole Stav je přidělenou volajícím.  
  
 Integrované vývojové prostředí používá tuto funkci před přejmenování adresáře ke kontrole, jestli adresář je pod správou zdrojových kódů dotazem, zda má odpovídajícího projektu. Pokud adresář není pod správou zdrojových kódů, rozhraní IDE zadat správné upozornění pro uživatele.  
  
> [!NOTE]
>  Pokud není implementovat jednu nebo více hodnot stavu vybere možnost plug-in správy zdrojových kódů, neimplementovaná bity je třeba nastavit na hodnotu nula.  
  
## <a name="see-also"></a>Viz také:  
 [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Adresář stavový kód](../extensibility/directory-status-code-enumerator.md)