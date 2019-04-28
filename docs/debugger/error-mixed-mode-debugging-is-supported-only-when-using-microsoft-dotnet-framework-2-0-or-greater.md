---
title: 'Chyba: Ladění ve smíšeném režimu je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 2.0 nebo vyšší. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2fb4d0dfaeb944700757c9ceec222dbd62dab9dd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850680"
---
# <a name="error-mixed-mode-debugging-is-supported-only-when-using-microsoft-net-framework-20-or-greater"></a>Chyba: Ladění ve smíšeném režimu je podporované, jenom pokud používáte rozhraní Microsoft .NET Framework 2.0 nebo vyšší.
Chcete-li ladit smíšené nativního a spravovaného kódu, musíte mít [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze 2.0, 3.0. 3.5 nebo 4.0. Ladění ve smíšeném režimu s předchozími verzemi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] se nepodporuje.

### <a name="to-correct-this-error"></a>Oprava této chyby

- Upgrade [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] na verzi 2.0, 3.0, 3.5 nebo 4.0.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)