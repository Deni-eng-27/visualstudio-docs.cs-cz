---
title: Sccdirqueryinfo – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b86ac7c701f96d467f0c059fc7e4b732699b1da5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758995"
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce zkontroluje seznam plně kvalifikovaných adresářů pro jejich aktuální stav.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parametry  
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
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Kód stavu adresáře](../extensibility/directory-status-code-enumerator.md)
