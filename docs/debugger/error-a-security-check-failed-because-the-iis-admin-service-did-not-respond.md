---
title: 'Chyba: Kontrola zabezpečení selhala, protože služba správy služby IIS neodpověděla. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21329a89e5ca6971143de9cf76d357be0f86e9ab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54992591"
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>Chyba: Kontrola zabezpečení selhala, protože služba správy služby IIS neodpověděla.
Tato chyba nastane, pokud správce služby IIS neodpovídá. To obvykle znamená, že dojde k problému s instalací služby IIS. Nejprve ověří, zda je spuštěna služba pomocí **služby** nástroj z **nástroje pro správu**.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Znovu nainstalujte IIS pomocí **přidat nebo odebrat programy** ovládacích panelech.  
  
-   -nebo-  
  
-   Služba IIS odeberte z počítače, pomocí ovládacího panelu Přidat nebo odebrat programy. Pokud jste odebrali službu IIS a stále máte problémy, zkontrolujte registru a ujistěte se, že tento klíč už existuje:  
  
    `HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}`  
  
     -nebo-  
  
-   Zakážete službu Správce služby IIS pomocí nástroje pro správu ovládacích panelů. Tato akce zakáže služby IIS na vašem počítači.  
  
     Po provedení některé z těchto tří kroků, restartujte počítač.  
  
     Další informace najdete v dokumentaci služby IIS.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)