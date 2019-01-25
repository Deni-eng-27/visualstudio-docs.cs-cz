---
title: 'Chyba: Pracovní proces webu byl ukončen službou IIS | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.web_server_process_terminated
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5707b972-71a6-4cc6-ab99-c7c00ca8628c
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 97b6b7a798483000916ee8c99a8000fd45b9cc00
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800027"
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>Chyba: Pracovní proces webu byl ukončen službou IIS.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ladicí program zastavení provádění kódu na webu. Internetové informační služby (IIS) předpokládat, že má pracovní proces přestal reagovat. příčinou. Proto služba IIS byla ukončena pracovního procesu.  
  
 Chcete-li pokračovat v ladění, je nutné nakonfigurovat služby IIS umožňující pracovního procesu, abyste mohli pokračovat. Tato chybová zpráva se nezobrazí ve verzích služby IIS, která jsou starší než IIS 7.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>Ke konfiguraci služby IIS 7 umožňuje pracovního procesu pokračovat  
  
1. Otevřít **nástroje pro správu** okna.  
  
   1.  Klikněte na tlačítko **Start**a klikněte na tlačítko **ovládací panely**.  
  
   2.  V **ovládací panely**, zvolte **přepnout do klasického zobrazení**, v případě potřeby a potom dvakrát klikněte na panel **nástroje pro správu**.  
  
2. V **nástroje pro správu** okna, dvakrát klikněte na panel **Správce Internetové informační služby (IIS)**.  
  
    Otevře se Správce služby IIS.  
  
3. V **připojení** podokně rozbalte \<název počítače > uzel v případě potřeby.  
  
4. V části \<název počítače > uzel, klikněte na tlačítko **fondy aplikací**.  
  
5. V **fondy aplikací** seznamu, klikněte pravým tlačítkem na název fondu vaše aplikace spuštěná v a pak klikněte na tlačítko **Upřesnit nastavení**.  
  
6. V **Upřesnit nastavení** dialogové okno vyhledejte **Model procesu** části a proveďte jednu z následujících akcí:  
  
   - Nastavte **povolený příkaz Ping** k **False**.  
  
   - Nastavte **maximální prodleva příkazu Ping** na hodnotu, která je větší než 90 sekund.  
  
     Nastavení **povolený příkaz Ping** k **False** zabraňuje kontroluje, zda pracovní proces je pořád spuštěný a zachová pracovní proces aktivní, dokud jej nezastavíte laděného procesu služby IIS. Nastavení **maximální prodleva příkazu Ping** velké hodnoty umožňuje pokračovat v monitorování pracovní proces služby IIS.  
  
7. Klikněte na tlačítko **OK** zavřete **Upřesnit nastavení** dialogové okno.  
  
8. Zavřete Správce služby IIS a **nástroje pro správu** okna.  
  
## <a name="see-also"></a>Viz také  
 [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
