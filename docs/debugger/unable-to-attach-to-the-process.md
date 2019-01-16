---
title: Nelze se připojit k procesu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.remote.unable2attach
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: affcff981ee516810f2ed9f6c2337c5145ebc572
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "53819572"
---
# <a name="unable-to-attach-to-the-process"></a>Nelze připojit k procesu.
Nelze se připojit k procesu. Komponenty ladicího programu na server přijal při připojení k tomuto počítači byl zamítnut přístup.  
  
 Existují dva běžné scénáře, které způsobí tuto chybu:  
  
 **Scénář 1:** A počítač se systémem Windows XP. Počítač B používá Windows Server 2003. Registru v počítači B obsahuje následující hodnotu DWORD:  
  
 `HKLM\Software\Microsoft\MachineDebugManager\AllowLaunchAsOtherUser=1`  
  
 Uživatel 1 spustí relaci terminálového serveru (relace 1) v počítači B a spustí spravované aplikace z této relace.  
  
 Přihlášení uživatele 2, kdo je správce na obou počítačích, na počítač A. Odtud uživatel pokusí připojit k aplikaci spuštěné v relaci 1 na počítač B.  
  
 **Scénář 2:** Jeden uživatel je přihlášený dva počítače, A a B, ve stejné pracovní skupině v obou počítačích pomocí stejné heslo. Ladicí program je spuštěn v počítači A a pokusu o připojení ke spravované aplikaci běžící na počítač B. počítač A má **přístup k síti: Model sdílení a zabezpečení pro místní účty** nastavena na **hosta**.  
  
### <a name="to-solve-scenario-1"></a>Chcete-li vyřešit scénář 1  
  
-   Spuštění ladicího programu a spravované aplikace v rámci stejné uživatelské jméno a heslo.  
  
### <a name="to-solve-scenario-2"></a>Chcete-li vyřešit scénář 2  
  
1.  Z **Start** nabídce zvolte **ovládací panely**.  
  
2.  V Ovládacích panelech poklikejte na **nástroje pro správu**.  
  
3.  V okně nástroje pro správu, klikněte dvakrát na **místní zásady zabezpečení**.  
  
4.  V okně místní zásady zabezpečení, vyberte **místní zásady**.  
  
5.  V **zásady** sloupce, klikněte dvakrát na **přístup k síti: Model sdílení a zabezpečení pro místní účty**.  
  
6.  V **přístup k síti: Model sdílení a zabezpečení pro místní účty** dialogové okno pole, změňte nastavení zabezpečení na **Classic**a klikněte na tlačítko **OK**.  
  
    > [!CAUTION]
    >  Změna modelu zabezpečení a klasickým modelem může způsobit neočekávaný přístup ke sdíleným souborům a komponenty DCOM. Pokud tuto změnu ověřit vzdáleného uživatele s vaší místní uživatelský účet a spíše než hosta. Pokud vzdálený uživatel odpovídá uživatelské jméno a heslo, tento uživatel bude mít přístup k žádné složky nebo objekt modelu DCOM, se kterými jste sdíleli navýšení kapacity. Pokud používáte tento model zabezpečení, ujistěte se, že všechny uživatelské účty na počítači silná hesla nebo nastavení ostrůvku izolované sítě pro ladění a ladit počítače před neoprávněným přístupem.  
  
7.  Zavřete všechna okna.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)