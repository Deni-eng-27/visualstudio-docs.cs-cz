---
title: Enumerátor zpráv | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 17c6d8a59a90b9744d2eb0ad96686db8da4e824b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53939898"
---
# <a name="message-enumerator"></a>Enumerátor zpráv
Následující příznaky se používají pro `TEXTOUTPROC` funkce, což je funkce zpětného volání, která poskytuje integrované vývojové prostředí při volání [sccopenproject –](../extensibility/sccopenproject-function.md) (naleznete v tématu [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) podrobnosti o zpětné volání funkce).  
  
 Pokud integrovaného vývojového prostředí se zobrazí výzva, proces zrušení, může zobrazit jedna z zprávy Storno. V tomto případě používá modul plug-in ovládací prvek zdroje `SCC_MSG_STARTCANCEL` žádat rozhraní IDE zobrazíte **zrušit** tlačítko. Potom může být odeslán libovolnou sadu normální zprávy. Pokud některý z těchto vrátí `SCC_MSG_RTN_CANCEL`, modul plug-in operace se ukončí a vrátí. Modul plug-in také dotazuje `SCC_MSG_DOCANCEL` pravidelně k určení, pokud uživatel operaci zrušil. Když se provádějí všechny operace, nebo pokud uživatel zrušil, modul plug-in odešle `SCC_MSG_STOPCANCEL`. `SCC_MSG_INFO`, SCC_MSG_WARNING, a SCC_MSG_ERROR typy se používají pro zprávy, která se zobrazí v posuvný seznam zpráv. `SCC_MSG_STATUS` je speciální typ, který označuje, že text by se zobrazit na stavovém řádku nebo dočasné oblasti. Není trvale zůstanou v seznamu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum {   
   SCC_MSG_RTN_CANCEL = -1,   
   SCC_MSG_RTN_OK = 0,   
   SCC_MSG_INFO = 1   
   SCC_MSG_WARNING,   
   SCC_MSG_ERROR,   
   SCC_MSG_STATUS,   
   SCC_MSG_DOCANCEL,   
   SCC_MSG_STARTCANCEL,   
   SCC_MSG_STOPCANCEL   
};  
```  
  
## <a name="members"></a>Členové  
 SCC_MSG_RTN_CANCEL  
 Návrat z zpětného volání k označení zrušit.  
  
 SCC_MSG_RTN_OK  
 Vrátí ze zpětného volání, abyste mohli pokračovat.  
  
 SCC_MSG_INFO  
 Zpráva je informační.  
  
 SCC_MSG_WARNING  
 Zpráva se upozornění.  
  
 SCC_MSG_ERROR  
 Zpráva se o chybu.  
  
 SCC_MSG_STATUS  
 Zpráva je určená pro stavový řádek.  
  
 SCC_MSG_DOCANCEL  
 Žádný text. Vrátí IDE `SCC_MSG_RTN_OK` nebo `SCC_MSG_RTN_CANCEL`.  
  
 SCC_MSG_STARTCANCEL  
 Zahájí cyklus Storno.  
  
 SCC_MSG_STOPCANCEL  
 Ukončí smyčku Storno.  
  
## <a name="see-also"></a>Viz také:  
 [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)