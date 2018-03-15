---
title: "Zachování zabezpečení aplikací v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- unauthorized access
- Baseline Security Analyzer
- Microsoft Baseline Security Analyzer
- security [.NET Framework], best practices
- MBSA (Microsoft Baseline Security Analyzer)
- security [.NET Framework], maintaining after deployment
ms.assetid: 621d10c1-842b-4902-be60-bb9719591751
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f0594f7c9af507f2c68ac4f0cc80b1d2e38d2a51
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="maintaining-security"></a>Správa zabezpečení

Často se říká, že cenou zabezpečení je neustálá bdělost. Navzdory maximální pozornosti věnované zabezpečení během navrhování a vývoje vaší aplikace byste měli předpokládat, že se po nasazení objeví určité problémy se zabezpečením. Auditováním aplikace a analýzou protokolů událostí můžete objevit některé dříve skryté závady.

Musíte být nejen ostražití ve vztahu ke své aplikaci, ale musíte mít také přehled o aktuálních bezpečnostních hrozbách a nedostatcích v případě platformy, na které aplikace běží, a v případě ostatních produktů, na kterých vaše aplikace závisí.

[Účty, zabezpečení a ochrany osobních údajů](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;získat pomoc s zabezpečení, ochrany osobních údajů a uživatelské účty, včetně informací o viry, hesla, rodičovské kontroly, brány firewall a jednotky šifrování...

[Bulletiny aktualizace zabezpečení](https://technet.microsoft.com/security/bulletins.aspx)&mdash;Tato stránka umožňuje snadno najít dřív vydané bulletiny. Bulletiny zabezpečení jsou určeny pro odborníky v oblasti IT a poskytují podrobné informace o aktualizacích zabezpečení.

[Microsoft Baseline Security Analyzer](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;Microsoft Baseline Security Analyzer (MBSA) je nástroj, který umožňuje jednotlivé domácí uživatel, podnikové uživatele nebo správce ke kontrole jedné nebo více založené na Windows počítačích běžné chyby konfigurace zabezpečení.