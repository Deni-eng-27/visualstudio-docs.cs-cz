---
title: Omezení ladění WCF | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3faa57a0a2ca413898364c2d4ad1891df85f1ce8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68176803"
---
# <a name="limitations-on-wcf-debugging"></a>Omezení ladění WCF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Existují tři způsoby, jak můžete začít s laděním služby WCF:  
  
- Ladíte klientský proces, který volá službu. Ladicí program kroky do služby. Služba nemusí být ve stejném řešení jako vaše klientská aplikace.  
  
- Ladíte klientský proces, který vytváří požadavek na službu. Služba musí být součástí vašeho řešení.  
  
- Pomocí **připojit k procesu** se připojíte ke službě, která je aktuálně spuštěná. Ladění začíná v rámci služby.  
  
  V tomto tématu jsou popsána omezení těchto scénářů.  
  
## <a name="limitations-on-stepping-into-a-service"></a>Omezení krokování na službu  
 Pro krokování služby z klientských aplikací, které ladíte, musí být splněny následující podmínky:  
  
- Klient musí volat službu pomocí synchronního objektu klienta.  
  
- Operace kontraktu nemůže být jednosměrná.  
  
- Pokud je server asynchronní, nemůžete zobrazit plný zásobník volání při provádění kódu uvnitř služby.  
  
- Ladění musí být povoleno s následujícím kódem v souboru app.config nebo Web.config:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    </system.web>  
    ```  
  
     Tento kód se musí přidat jenom jednou. Tento kód můžete přidat úpravou souboru. config nebo připojením ke službě pomocí **připojit k procesu**. Použijete **-li ke zpracování ve službě připojit k procesu** , kód ladění je automaticky přidán do souboru. config. Potom můžete do služby ladit a krokovat bez nutnosti upravovat soubor. config.  
  
## <a name="limitations-on-stepping-out-of-a-service"></a>Omezení krokování ze služby  
 Krokování ze služby a zpátky na klienta má stejná omezení, která jsou popsaná pro krokování do služby. Kromě toho musí být ladicí program připojen ke klientovi. Při ladění klienta a krokování do služby zůstane ladicí program připojen ke službě. To platí bez ohledu na to, jestli jste klienta spustili pomocí možnosti **Spustit ladění** nebo připojit k klientovi pomocí možnosti **připojit k procesu**. Pokud jste zahájili ladění připojením ke službě, ladicí program ještě není připojen ke klientovi. V takovém případě, pokud musíte krok ze služby a zpátky na klienta, musíte nejprve použít **připojit k procesu** a připojit se k klientovi ručně.  
  
## <a name="limitations-on-automatic-attach-to-a-service"></a>Omezení automatického připojení ke službě  
 Automatické připojení ke službě má následující omezení:  
  
- Služba musí být součástí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení, které ladíte.  
  
- Služba musí být hostovaná. Může být součástí projektu webu (systém souborů a HTTP), projektu webové aplikace (systému souborů a protokolu HTTP) nebo projektu knihovny služby WCF. Projekty knihovny služby WCF můžou být buď knihovny služeb nebo knihovny služby pracovního postupu.  
  
- Služba musí být vyvolána z klienta WCF.  
  
- Ladění musí být povoleno s následujícím kódem v souboru app.config nebo Web.config:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    <system.web>  
    ```  
  
## <a name="self-hosting"></a>Samoobslužné hostování  
 *Samoobslužná služba* je služba WCF, která neběží ve službě IIS, hostiteli služby WCF ani [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] vývojovém serveru. Informace o tom, jak ladit samoobslužné služby, naleznete v tématu [How to: Debug a on-Hosted Service WCF](../debugger/how-to-debug-a-self-hosted-wcf-service.md).  
  
## <a name="self-hosting"></a>Samoobslužné hostování  
 Aby bylo možné povolit ladění [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikací 3,0 nebo 3,5, je [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] nutné před instalací nástroje 3,0 nebo 3,5 nainstalovat [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] . Pokud [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] je nainstalována před [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 3,0 nebo 3,5, dojde k chybě při pokusu o ladění [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikace 3,0 nebo 3,5. Chybová zpráva: "nelze automaticky krokovat se serverem." Chcete-li tento problém vyřešit, opravte instalaci pomocí **ovládacích panelů**systému Windows, **programů a funkcí** [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .  
  
## <a name="see-also"></a>Viz také  
 [Ladění služeb WCF](../debugger/debugging-wcf-services.md)   
 [Postupy: Ladění služby WCF s vlastním hostováním](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
