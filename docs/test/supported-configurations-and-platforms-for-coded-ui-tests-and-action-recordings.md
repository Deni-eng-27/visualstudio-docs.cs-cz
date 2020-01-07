---
title: Konfigurace a platformy pro programové testy uživatelského rozhraní
ms.date: 10/04/2015
ms.topic: reference
helpviewer_keywords:
- coded UI tests
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 54c2ec423653d1649e7bac9dd302c5f272731477
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75594055"
---
# <a name="supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings"></a>Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a záznamy akcí

Podporované konfigurace a platformy pro programové testy uživatelského rozhraní pro Visual Studio Enterprise jsou uvedeny v následující tabulce. Tyto konfigurace platí i pro záznamy akcí vytvořené pomocí [!INCLUDE[MTRlong](../test/includes/mtrlong_md.md)].

> [!NOTE]
> Programový test UI musí mít stejná oprávnění jako testovaná aplikace.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**Požadavky**

- Visual Studio Enterprise

## <a name="supported-configurations"></a>Podporované konfigurace

| Konfigurace | Podporované |
|-| - |
| Operační systémy: | [!INCLUDE[win7](../debugger/includes/win7_md.md)]<br /><br /> [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]<br /><br /> [!INCLUDE[win8](../debugger/includes/win8_md.md)]<br /><br /> Windows 10 |
| Podpora 32bitové/64bitové verze | 32-bitový systém Windows, na kterém běží 32-bit [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], může testovat 32-bitové aplikace.<br /><br /> 64-bitový systém Windows, na kterém běží 32-bit [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], může testovat aplikace s 32-bit WOW, které mají uživatelské rozhraní synchronizace. n.<br /><br /> 64-bitový systém Windows, na kterém běží 32-bit [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], může testovat 64 model Windows Forms a aplikace WPF, které nemají k dispozici synchronizaci uživatelského rozhraní. |
| Architektura | x86 a x64 **Poznámka:** Internet Explorer není podporován v 64ovém režimu s výjimkou spuštění v [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novějších verzích. |
| .NET | .NET 2.0, 3.0, 3.5, 4 a 4.5. **Poznámka:** [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] a Visual Studio budou vyžadovat fungování rozhraní .NET 4. Nicméně aplikace vyvinuté pomocí uvedených verzí rozhraní .NET jsou podporovány. |

> [!NOTE]
> *Synchronizace uživatelského rozhraní* je funkce, kde je ověřeno přehrávání ve frontě zpráv každého ovládacího prvku. Pokud ovládací prvek neodpověděl na událost, která mu byla zaslána, událost je odeslána znovu.

## <a name="platform-support"></a>Podpora platformy

| Platforma | Úroveň podpory |
|-| - |
| Aplikace Windows Phone | Podporují se jenom telefonní aplikace založené na WinRT-XAML. |
| Aplikace pro UPW | Podporují se jenom aplikace UWP založené na jazyce XAML. |
| Univerzální aplikace pro Windows | Podporují se jenom univerzální aplikace pro Windows založené na jazyce XAML na telefonu a na ploše. |
| Edge | Záznam kroků akce nebo použití Tvůrce k zobrazení vlastností objektu není podporován. Testy lze přehrát v prohlížeči Edge pomocí sady Visual Studio 2015 Update 2 a novějších verzí pomocí rozšíření programového [testování uživatelského rozhraní v různých prohlížečích](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting). |
| Internet Explorer 8<br /><br /> Internet Explorer 9<br /><br /> Internet Explorer 10 **– Důležité:** Internet Explorer 10 se podporuje jenom na ploše. <br /><br /> Internet Explorer 11 **– Důležité:** Internet Explorer 11 je podporován pouze na ploše. | Plně podporováno.<br /><br /> **Podpora jazyka HTML5 v aplikaci Internet Explorer 9 a Internet Explorer 10:** kódované testy UI podporují záznam, přehrávání a ověřování ovládacích prvků HTML5: zvuk, video, ProgressBar a posuvník. -    Další informace naleznete v tématu [použití ovládacích prvků HTML5 v programových testech UI](../test/using-html5-controls-in-coded-ui-tests.md). **Upozornění:**      Pokud vytvoříte programové testy UI v aplikaci Internet Explorer 10, nemusí být spuštěny pomocí aplikace Internet Explorer 9 nebo Internet Explorer 8. Je to proto, že aplikace Internet Explorer 10 obsahuje ovládací prvky HTML5, jako je Zvuk, Video, Indikátor průběhu a Posuvník. Tyto ovládací prvky jazyka HTML5 nejsou rozpoznány aplikací Internet Explorer 9 nebo Internet Explorer 8. Podobně váš programový test UI pomocí aplikace Internet Explorer 9 může zahrnovat některé ovládací prvky jazyka HTML5, které aplikace Internet Explorer 8 nerozpozná.<br />-   **Podpora kontroly pravopisu v aplikaci Internet Explorer 10:** Internet Explorer 10 obsahuje možnosti kontroly pravopisu pro všechna textová pole. Můžete provádět výběr ze seznamu navrhovaných oprav. Programový test UI bude ignorovat akce uživatele, jako je volba návrhu alternativního pravopisu. Bude zaznamenán pouze konečný text zadaný do textového pole.<br />     Tyto akce jsou zaznamenány pro programový test UI používající ovládací prvek kontroly pravopisu: Přidat do slovníku, Kopírovat, Vybrat vše, Přidat do slovníku a Ignorovat.<br />**podpora -   pro 64 aplikace Internet Explorer spuštěná v systému Windows 8:** dříve, 64 verze aplikace Internet Explorer pro nahrávání a přehrávání se nepodporují. U [!INCLUDE[win8](../debugger/includes/win8_md.md)] a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]byly v programovém testu UI povoleny 64 verze aplikace Internet Explorer. **Upozornění:** podpora architektury 64 pro Internet Explorer platí pouze v případě, že používáte [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novější.<br />-   **podporu připnutých webů v aplikaci Internet Explorer 9:** v aplikaci Internet Explorer 9 byly zavedeny připnuté weby. Díky funkci Připnuté weby se můžete dostat na své oblíbené weby přímo z hlavního panelu systému Windows – bez nutnosti nejdříve spustit aplikaci Internet Explorer. Programové testy UI nyní mohou generovat akce podporující záměr na připnutých webech. Další informace o připnuté weby najdete v tématu [připnuté weby](https://support.microsoft.com/hub/4230784/internet-explorer-help).<br />-   **Podpora pro sémantické značky v aplikaci Internet Explorer 9:** aplikace Internet Explorer 9 zavedla následující sémantické značky: oddíl, NAV, článek, zrušení, HGroup, záhlaví, zápatí, obrázek, figcaption a značka. Programové testy UI ignorují během záznamu všechny tyto sémantické značky. Pomocí Tvůrce programového testu UI můžete přidat do těchto značek kontrolní výrazy. K procházení všech těchto prvků a zobrazení jejich vlastností můžete použít Navigační vytáčení v Tvůrci programového testu UI.<br />-   **bezproblémového zpracování prázdných znaků mezi verzemi aplikace Internet Explorer:** existují rozdíly v zacházení s prázdnými znaky mezi Internet Explorer 8, Internet Explorer 9 a Internet Explorer 10. Programový test UI zpracovává tyto rozdíly bez problémů. Proto se například bude programový test UI vytvořený v aplikaci Internet Explorer 8 přehrávat úspěšně v aplikaci Internet Explorer 9 a Internet Explorer 10.<br />-   **oznamovací oblast aplikace Internet Explorer je nyní zaznamenána s nastaveným atributem "pokračovat na chybu":** všechny akce v oznamovací oblasti aplikace Internet Explorer jsou nyní zaznamenávány s nastaveným atributem "pokračovat na chybu". Pokud se během přehrávání nezobrazí panel oznámení, akce na něm budou ignorovány a programový test UI bude pokračovat další akcí. |
| Ovládací prvky rozhraní Windows Forms a WPF třetích stran | Plně podporováno.<br /><br /> Chcete-li povolit ovládací prvky třetích stran v rozhraních Windows Forms a WPF, musíte přidat odkazy a kód. Další informace naleznete v tématu [Povolení programového testování uživatelského rozhraní pro vaše ovládací prvky](../test/enable-coded-ui-testing-of-your-controls.md). |
| Internet Explorer 6<br /><br /> Internet Explorer 7 | Není podporováno. |
| Chrome<br /><br /> Firefox | Záznam kroků akcí není podporován. Programové testy UI můžete přehrát v prohlížečích Chrome a Firefox, pokud používáte sadu Visual Studio 2012 s aktualizací 4 nebo novější. Další podrobnosti najdete [zde](using-different-web-browsers-with-coded-ui-tests.md). |
| Opera<br /><br /> Safari | Není podporováno. |
| Silverlight | Není podporováno.<br /><br /> Pro Visual Studo 2013 však můžete stáhnout [modul plug-in programového testu uživatelského rozhraní Microsoft Visual Studio 2013 pro program Silverlight](https://go.microsoft.com/fwlink/?LinkId=691026) z galerie sady Visual Studio. |
| Flash nebo Java | Není podporováno. |
| Windows Forms 2.0 a vyšší | Plně podporováno. **Poznámka:**  Ovládací prvky NetFx jsou plně podporovány, ale ne všechny ovládací prvky třetích stran jsou podporovány. |
| WPF 3.5 a novější | Plně podporováno.<br /><br /> **Poznámka:** Ovládací prvky NetFx jsou plně podporovány, ale ne všechny ovládací prvky třetích stran jsou podporovány. |
| Windows Win32 | Může pracovat s některými známými problémy, ale není oficiálně podporována. |
| MFC | Částečně podporováno. Podrobnosti o podporovaných funkcích najdete v [UITest Framework](https://blogs.msdn.microsoft.com/vstsqualitytools/2010/04/15/uitest-framework-mfc-support-in-vs-2010/) . |
| SharePoint | Plně podporováno. |
| Klientské aplikace Office | Není podporováno. |
| Webový klient Dynamics CRM | Plně podporováno. |
| Klient Dynamics (Ax) 2012 | Záznam a přehrávání akce jsou podporovány jen částečně. Podrobnosti najdete v tématu Podpora programového [uživatelského rozhraní a záznamů akce sady Visual Studio 10 pro Microsoft Dynamics](https://blogs.msdn.microsoft.com/dave_froslie/2011/09/01/visual-studio-10-coded-ui-action-recordings-support-for-microsoft-dynamics-ax-2012/) . |
| SAP | Není podporováno. |
| Citrix/Terminálové služby | Nedoporučujeme nahrávat akce na terminálový server. Zapisovač nepodporuje spouštění více instancí současně. |
| PowerBuilder | Částečně podporováno.<br /><br /> Podpora se provádí v rozsahu, ve kterém je povoleno usnadnění pro ovládací prvky aplikace PowerBuilder. |

Informace o tom, jak vytvořit rozšíření pro podporu jiných platforem, naleznete v tématu Povolení programového [testování uživatelského rozhraní pro vaše ovládací prvky](../test/enable-coded-ui-testing-of-your-controls.md) a rozšíření programových [testů uživatelského rozhraní a záznamů akcí](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md).

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
