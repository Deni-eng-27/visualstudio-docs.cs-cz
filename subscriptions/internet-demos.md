---
title: Použití kódů Product Key k podpoře internetových ukázek prostřednictvím Terminálové služby | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/19/2019
ms.topic: conceptual
description: Naučte se používat kódy Product Key k podpoře internetových ukázek prostřednictvím Terminálové služby a povolení přístupu k VP.
ms.openlocfilehash: 19faa64b7eeaebc1b92ca965f686795b31e00e7e
ms.sourcegitcommit: 9fc8b144d4ed1c46aba87c0b7e1d24454e0eea9d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68493386"
---
# <a name="internet-demonstrations-via-terminal-services"></a>Internetové ukázky prostřednictvím Terminálové služby
Pomocí předplatného sady Visual Studio můžete koncovým uživatelům poskytnout přístup k internetovým demonstračním programům prostřednictvím Terminálové služby (Windows Server 2003 nebo Windows Server 2008) nebo služby Vzdálená plocha (Windows Server 2008 R2 a novější). Tímto způsobem můžou k vašemu předvádění přistupovat až 200 anonymních uživatelů. Vaše ukázka nesmí používat produkční data. Předplatitelé sady Visual Studio mají licenci k předvedení svých aplikací koncovým uživatelům. Tato internetová ukázka pomocí Terminálové služby (TS) nebo služby Vzdálená plocha (RDS) je jediným scénářem, kdy koncoví uživatelé bez předplatného sady Visual Studio můžou pracovat s demonstrační aplikací, když je software licencovaný prostřednictvím vizuálu. Předplatná studia.

To je kromě práv pro vývoj a testování, kde předplatitelé sady Visual Studio můžou podle potřeby používat tolik připojení k VP nebo TS.

## <a name="enabling-rds-access"></a>Povolení přístupu k VP
Předplatitelé sady Visual Studio můžou zvýšit počet uživatelů, kteří mají přístup k Windows serveru přes RDS, zadáním kódu Product Key, který je zadaný na kartě [kódy Product](https://my.visualstudio.com/productkeys?wt.mc_id=o~msft~docs) Key na [portálu odběratele](https://my.visualstudio.com?wt.mc_id=o~msft~docs). Pokud chcete získat kód Product Key, připojte se ke stránce kódy Product Key a posuňte se dolů na verzi Windows serveru, kterou používáte. Vyhledejte možnost Windows Server < verze > R2 Vzdálená plocha < uživatele nebo zařízení > připojení a klikněte na odkaz **klíč deklarace** . Pokud například používáte službu Vzdálená plocha v systému Windows Server 2012 R2 a nasazení používá licence CAL uživatele, vyberte možnost připojení uživatele služby Vzdálená plocha systému Windows Server 2012 (50).
Pro Windows Server 2008 R2 je k dispozici pět klíčů každého typu a každý klíč bude podporovat 20 připojení. Pro Windows Server 2012 R2 jsou k dispozici čtyři klíče pro každý typ a budou podporovat připojení 50.

## <a name="to-enable-additional-connections-in-windows-server"></a>Povolení dalších připojení v systému Windows Server:
1. Spusťte Správce serveru.
2. V levém navigačním podokně otevřete seznam servery.
3. Klikněte pravým tlačítkem na licenční server a vyberte "instalovat licence".
4. Postupujte podle kroků v průvodci.  Když vybíráte typ smlouvy, zvolte License Pack (maloobchodní prodej) a zadejte kód Product Key, který jste získali z portálu MY.

Koncoví uživatelé se můžou k aplikacím přistupovat přes RDS, pokud jsou splněné následující podmínky:
- Uživatelé musí být anonymní (v neověřeném stavu).
- Připojení musí být přes Internet.
- Pro ukázky aplikace lze použít až 200 souběžných uživatelských připojení.
- Kódy Product Key pro povolení připojení uživatele musí získat předplatitel sady Visual Studio.

## <a name="next-steps"></a>Další kroky
Pokud potřebujete pokyny k nasazení služby RDS, Projděte si část blogové řady pro https://techcommunity.microsoft.com/t5/Ask-The-Performance-Team/bg-p/AskPerf **službu Vzdálená plocha (RDS) 2012 v části nasazení relace vzdálené plochy** . 

Pokud máte nějaké dotazy, navštivte [fórum služby Vzdálená plocha Microsoft Services](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS).
