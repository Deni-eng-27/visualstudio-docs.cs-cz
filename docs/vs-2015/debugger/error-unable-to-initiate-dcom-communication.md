---
title: 'Chyba: Nepovedlo se inicializovat komunikaci modelu DCOM | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.unmarshal_server_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 514f4e3de9bd5b79387a17dffe0e016dc92ea91e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54761118"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Chyba: Nelze inicializovat komunikaci modelu DCOM.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při místní počítač se pokusil komunikovat se vzdáleným počítačem došlo k chybě modelu DCOM. To je způsobeno brány firewall na vzdálený server nebo porušený ověřování Windows na vzdáleném počítači.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud vzdálený počítač má povolenou bránu Windows Firewall, přečtěte si téma [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
-   Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)
