---
title: 'Chyba: Prostředí ASP.NET není nainstalováno | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 31268b94ab632e598badcba3def387ef1fc2ba1d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752201"
---
# <a name="error-aspnet-not-installed"></a>Chyba: Prostředí ASP.NET není nainstalováno
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K této chybě dochází při [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] není správně nainstalován v počítači, který se pokoušíte ladit. To může znamenat, že [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] nebyl nikdy nainstalován nebo které [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] byla nainstalovaná jako první a služby IIS byl nainstalován později.  
  
### <a name="to-reinstall-aspnet"></a>K opětovné instalaci technologie ASP.NET  
  
1.  Z okna příkazového řádku spusťte následující příkaz:  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     kde *verze* představuje číslo verze rozhraní .NET Framework nainstalované v počítači, jako je například v1.0.370. Můžete určit verzi rozhraní framework hledání `\WINDOWS\Microsoft.NET\Framework` adresáře.  
  
    > [!NOTE]
    >  Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
