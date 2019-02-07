---
title: Program Zlepšování softwaru a služeb na základě zkušeností uživatelů
description: Zjistěte, jak spravovat nastavení ochrany osobních údajů v sadě Visual Studio.
ms.date: 05/21/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 96ddafa340f0d9ab87b359cf1a5cc5b92ea7cabe
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55852670"
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Visual Studio programu zlepšování zkušeností zákazníků

Visual Studio zákazníka prostředí pro zlepšování programu (VSCEIP) je navržená můžete pomoci společnosti Microsoft, vylepšení sady Visual Studio v čase. Tento program [shromažďuje informace o chybách](../ide/diagnostic-data-collection.md), počítačový hardware, a jak ostatní používají Visual Studio, aniž by to ovlivnilo uživatele ve své úkoly v počítači. Shromažďované informace pomáhají společnosti Microsoft určit funkce, které ke zlepšení. Tento dokument obsahuje postup pro aktivování nebo zrušení VSCEIP.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

## <a name="opt-in-or-out"></a>Optimalizované snížení nebo navýšení kapacity

VSCEIP je ve výchozím nastavení zapnutá. Můžete ji vypnout nebo zpět na, podle těchto pokynů:

1. Spusťte Visual Studio.

1. Z **pomáhají** nabídky, přejděte k **odeslat zpětnou vazbu**a pak vyberte **nastavení**.

   **Programu zlepšování zkušeností sady Visual Studio** zobrazí se dialogové okno.

1. Chcete-li odhlásit, vyberte **Ne, nechci se zúčastnit**a pak vyberte **OK**.
   Chcete-li vyjádřit výslovný souhlas, vyberte **Ano, chci se zúčastnit**a pak vyberte **OK**.

   ![Dialogové okno Visual Studio na základě zlepšení zkušeností](media/experience-improvement-program.png)

### <a name="registry-settings"></a>Nastavení registru

Pokud nainstalujete [Build Tools pro Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017), je nutné aktualizovat registr a nakonfigurujte VSCEIP. Podnikoví zákazníci můžete vytvořit zásady skupiny pro aktivování nebo zrušení VSCEIP nastavením zásady založené na registru.

Příslušný klíč registru a nastavení jsou následující:

V operačním systému 64-bit, klíč = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\15.0\SQM** na 32bitovém operačním systému, klíč = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\15.0\SQM** zásad skupiny v případě je povoleno, klíč = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM**

Položka = **OptIn**

Hodnota = (DWORD)
- **0** je vyjádřil se výslovný nesouhlas (vypnout VSCEIP)
- **1** přihlášení (zapnout VSCEIP)

> [!CAUTION]
> Pokud chybně upravíte registr, může dojít k vážnému poškození systému. Před provedením změn v registru doporučujeme zálohovat všechna důležitá data v počítači. Můžete také použít **poslední známá funkční konfigurace** možnost spuštění, pokud narazíte na potíže po ručně provedených změnách.

Další informace o údajích shromažďovaných, zpracovávaných a přenášených podle VSCEIP, naleznete v tématu [prohlášení o ochraně osobních údajů Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Viz také:

* [Diagnostické informace shromážděné funkcí sady Visual Studio](diagnostic-data-collection.md)
* [Kontaktujte nás](../ide/talk-to-us.md)
* [Postup ohlášení problému se sadou Visual Studio](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Visual Studio Developer Community](https://developercommunity.visualstudio.com/)
* [Prohlášení o ochraně osobních údajů společnosti Microsoft](https://privacy.microsoft.com/privacystatement)
