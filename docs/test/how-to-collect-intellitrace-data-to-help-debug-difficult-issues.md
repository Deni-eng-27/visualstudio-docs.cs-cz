---
title: IntelliTrace data
ms.date: 10/13/2016
ms.topic: conceptual
helpviewer_keywords:
- IntelliTrace, configuring test settings
- Diagnostic Data Adapter, InteliTrace
- debugging [Visual Studio ALM], difficult issues using IntelliTrace
- Test Runner, InteliTrace
ms.assetid: 02b6716f-569e-4961-938a-e790a0c74b5c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: adc77ee87bbbf07d04fd7c01a554c7c074e5bf7f
ms.sourcegitcommit: 5d1b2895d3a249c6bea30eb12b0ad7c0f0862d85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/08/2020
ms.locfileid: "80880218"
---
# <a name="how-to-collect-intellitrace-data-to-help-debug-difficult-issues"></a>Postup: Shromažďování dat IntelliTrace, které vám pomohou při ladění obtížných problémů

Adaptér diagnostických dat pro intelliTrace můžete nakonfigurovat tak, aby shromažďoval konkrétní informace o trasování diagnostiky v sadě Visual Studio. Testy mohou tento adaptér používat. Test může shromažďovat podstatné diagnostické události aplikace, které může vývojář později použít pro trasování skrze kód a nalezení příčiny chyby. Adaptér diagnostiky dat pro technologii IntelliTrace lze použít pro manuální, nebo automatizované testy.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

> [!NOTE]
> Technologie IntelliTrace pracuje pouze v aplikaci, která je napsána ve spravovaném kódu. Pokud testujete webovou aplikaci, která používá prohlížeč jako klienta, neměli byste povolit IntelliTrace pro klienta v nastavení testu, protože žádný spravovaný kód je k dispozici pro trasování. V takovém případě můžete chtít nastavit prostředí a vzdáleně shromažďovat data IntelliTrace na webovém serveru.

Data IntelliTrace jsou uložena v souboru, který má příponu *.iTrace*. Při spuštění testu a krok testu se nezdaří, můžete vytvořit chybu. Soubor IntelliTrace, který obsahuje diagnostické informace, je automaticky připojen k této chybě.

> [!NOTE]
> Adaptér diagnostiky dat pro technologii IntelliTrace nevytvoří soubor IntelliTrace, pokud test proběhne úspěšně. Soubor se uloží pouze při selhání testovacího případu nebo při odeslání hlášení o chybě.

Data shromažďovaná do souboru IntelliTrace zvyšují efektivitu ladění zkrácením doby potřebné k reprodukci a diagnostice chyby v kódu. Navíc vzhledem k tomu, že soubor IntelliTrace lze sdílet s jinou osobou, která může replikovat místní relaci ve svém počítači, se snižuje pravděpodobnost, že chyby nebudou reprodukovatelné.

> [!NOTE]
> Pokud v nastaveních testů povolíte technologii IntelliTrace, nebude fungovat shromažďování dat o pokrytí kódu.

> [!WARNING]
> Adaptér diagnostiky dat pro technologii IntelliTrace funguje díky instrumentaci spravovaného procesu, která musí být provedena po načtení testů pro testovací běh. Pokud již byl proces, který chcete sledovat, spuštěn, nebudou shromážděny žádné soubory IntelliTrace, protože proces již probíhá. To lze obejít ověřením, že se proces před načtením testů ukončil. Poté po načtení testů nebo spuštění prvního testu spusťte proces.

::: moniker range="vs-2017"
Následující postup popisuje, jak nakonfigurovat data IntelliTrace, která chcete shromažďovat. Tyto kroky platí pro konfigurační editor v Microsoft Test Manager a Test Nastavení dialogového okna v sadě Visual Studio.
::: moniker-end
::: moniker range=">=vs-2019"
Následující postup popisuje, jak nakonfigurovat data IntelliTrace, která chcete shromažďovat. Tyto kroky platí pro dialogové okno Nastavení testu v sadě Visual Studio.
::: moniker-end

> [!NOTE]
> Uživatelský účet pro testovacího agenta, který je používán k shromažďování dat IntelliTrace, musí být členem skupiny administrátorů. Další informace naleznete v [tématu Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>Konfigurace dat pro shromažďování pomocí adaptéru diagnostických dat IntelliTrace

::: moniker range="vs-2017"
Před provedením kroků v tomto postupu je nutné otevřít nastavení testu ze správce testů společnosti Microsoft nebo sady Visual Studio a vybrat stránku **Data a diagnostika.**
::: moniker-end
::: moniker range=">=vs-2019"
Před provedením kroků v tomto postupu je nutné otevřít nastavení testu z aplikace Visual Studio a vybrat stránku **Data a diagnostika.**
::: moniker-end

### <a name="to-configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>Konfigurace dat pro shromažďování pomocí adaptéru diagnostických dat IntelliTrace

1. Vyberte roli, kterou chcete použít pro shromažďování dat IntelliTrace.

2. Vyberte **možnost IntelliTrace**.

3. Pokud přidáváte IntelliTrace pro roli webového klienta nebo pro ASP.NET webové aplikace, musíte také vybrat **ASP.NET proxy klienta pro IntelliTrace a Test Impact**.

     Tento proxy server umožňuje shromažďovat informace o volání http z klienta na webový server pro adaptéry diagnostických dat IntelliTrace a Test Impact.

    > [!WARNING]
    > Pokud se rozhodnete použít vlastní účet pro identitu, která se používá pro fond aplikací na serveru Internet Information Server (IIS), kde chcete shromažďovat data IntelliTrace, je nutné vytvořit místní profil uživatele v počítači služby IIS pro vlastní účet, který je používán. Místní profil lze pro vlastní účet vytvořit jednorázovým přihlášením na počítači se službou IIS místně, nebo spuštěním následujícího příkazu příkazového řádku pomocí vlastních pověření účtu:
    >
    > **runas /user:doména\název /profil cmd.exe**

4. **Chcete-li** změnit výchozí nastavení Technologie IntelliTrace, zvolte Konfigurovat pro **intelliTrace.**

     Zobrazí se dialogové okno pro konfiguraci dat, která budou shromažďována.

    > [!WARNING]
    > Pokud povolíte shromažďování dat IntelliTrace, nebude fungovat shromažďování dat pokrytí kódu.

5. Zvolte **kartu Obecné.** Vyberte **události IntelliTrace pouze** pro záznam významných diagnostických událostí, které mají minimální dopad na výkon při testování.

     -nebo-

     Vyberte **Události IntelliTrace a informace o volání** pro záznam diagnostických událostí a trasování úrovně metody, která zobrazuje informace o volání. Tato úroveň trasování může mít vliv na výkon při spuštění testů.

6. Chcete-li shromažďovat data z aplikace ASP.NET spuštěnou v Internetové informační službě, vyberte **možnost Shromažďovat data z ASP.NET aplikací spuštěných v Internetové informační službě**. Nastavte a nakonfigurujte testovacího agenta v roli webového serveru. Viz [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

7. Zvolte kartu **Moduly.** **Collect data from all modules except for the following** **Add** **Remove** Tato volba umožňuje zahrnout všechny moduly, které jsou spuštěny v systému kromě modulů, jež zadáte.

     -nebo-

     Vyberte **Shromažďovat data pouze z následujících modulů** a pomocí příkazu **Přidat** přidejte do seznamu modulů a **Odebrat** modul. Tato volba umožňuje přesně určit požadované moduly.

    > [!NOTE]
    > Pokud je to možné, vyberte konkrétní postupy, které chcete sledovat. To je doporučeno pro optimální výkon.

8. Zvolte kartu **Procesy.** Vyberte **Shromáždit data ze všech procesů s výjimkou následujících** procesů a pomocí **příkazu Přidat** přidejte do seznamu procesů a **Odebrat** proces odeberte. Tato volba umožňuje zahrnout všechny procesy, které jsou spuštěny v systému kromě procesů, jež zadáte.

     -nebo-

     Vyberte **Shromáždit data pouze z určených procesů** a pomocí příkazu **Přidat** přidejte do seznamu procesů a **Odebrat** proces odeberte. Tato volba umožňuje přesně určit požadované procesy.

9. (Nepovinné) Zvolte kartu **Události IntelliTrace.** Vyberte nebo zrušte zaškrtnutí každé kategorie událostí IntelliTrace, kterou chcete zahrnout nebo vyloučit při shromažďování diagnostických událostí.

10. (Volitelné) Rozbalte každou kategorii událostí IntelliTrace a zaškrtněte nebo zrušte zaškrtnutí každé konkrétní události, kterou chcete zahrnout nebo vyloučit v událostech IntelliTrace.

11. (Nepovinné) Zvolte kartu **Upřesnit.** Dále zvolte šipku vedle **položky Maximální velikost místa na disku pro nahrávání** a vyberte maximální velikost, kterou chcete povolit pro soubor IntelliTrace.

    > [!NOTE]
    > Pokud velikost pro záznam zvětšíte, může dojít k problému s vypršením času při ukládání tohoto záznamu společně s výsledky testů.

12. Pokud používáte Microsoft Test Manager (zastaralé v Sadě Visual Studio 2017), zvolte **Uložit**. Pokud používáte Visual Studio, zvolte **OK**. Nastavení technologie IntelliTrace je nyní nakonfigurováno a uloženo pro nastavení testů.

    ::: moniker range="vs-2017"
    > [!NOTE]
    > Chcete-li obnovit konfiguraci tohoto adaptéru diagnostických dat, zvolte **Obnovit na výchozí konfiguraci** pro sadu Visual Studio nebo **Obnovit výchozí** pro Správce testů společnosti Microsoft.
    ::: moniker-end
    ::: moniker range=">=vs-2019"
    > [!NOTE]
    > Chcete-li obnovit konfiguraci tohoto adaptéru diagnostických dat, zvolte **Obnovit výchozí konfiguraci** v sadě Visual Studio.
    ::: moniker-end

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických dat během testování (plány testů Azure)](/azure/devops/test/collect-diagnostic-data?view=vsts)
- [Shromažďování diagnostických dat v ručních testech (plány testů Azure)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts)
- [Shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Shromažďování dat IntelliTrace](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)
