---
title: 'Chyba: vzdálený počítač se nezobrazuje v dialogovém okně vzdálené připojení | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: error-reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ac49379f513f753592191632cd3edf1af89a9dc4
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2020
ms.locfileid: "85460595"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač se nezobrazuje v dialogovém okně Vzdálená připojení
Pokud se vzdálený počítač nezobrazí v dialogovém okně Vzdálená připojení, Projděte si následující běžné příčiny.

 Pokud používáte spravovaný režim kompatibility, podívejte se prosím do dokumentace k sadě Visual Studio 2010: [řešení potíží se vzdáleným laděním – Visual Studio 2010](/previous-versions/visualstudio/visual-studio-2010/2ys11ead(v=vs.100)).

### <a name="common-causes-for-this-error"></a>Běžné příčiny této chyby

- Vzdálený počítač běží na počítači, který je v jiné podsíti. Pokud to chcete opravit, ručně zadejte název počítače nebo IP adresu v dialogu kvalifikátor.

- Vzdálený ladicí program na vzdáleném počítači neběží. Chcete-li tento problém vyřešit, spusťte vzdálený ladicí program.

- Brána firewall blokuje komunikaci mezi Visual Studio a vzdáleným počítačem. Pokud to chcete opravit, nakonfigurujte bránu firewall tak, aby umožňovala aplikaci Visual Studio a vzdálený ladicí program (Msvsmon) komunikovat.

- Antivirový software blokuje komunikaci mezi Visual Studio a vzdáleným počítačem. Pokud to chcete opravit, nakonfigurujte antivirový software tak, aby umožňoval aplikaci Visual Studio a vzdálený ladicí program (Msvsmon) komunikovat.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)