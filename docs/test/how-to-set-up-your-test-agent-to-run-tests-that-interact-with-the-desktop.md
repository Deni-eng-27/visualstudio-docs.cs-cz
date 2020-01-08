---
title: Konfigurace testovacího agenta
ms.date: 09/18/2018
ms.topic: conceptual
helpviewer_keywords:
- agents, configuring for interaction with desktop
ms.assetid: 3a94dd07-6d17-402c-ae8f-7947143755c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f4ef2d589e75c50a6cecb5364d5b458cffdfd145
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75588964"
---
# <a name="how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop"></a>Postupy: nastavení testovacího agenta pro spouštění testů, které komunikují s plochou

Pokud chcete spustit automatizované testy, které spolupracují s plochou, je třeba nastavit agenta tak, aby se spouštěl jako proces namísto služby. Například pokud chcete vzdáleně spustit programový test UI pomocí testovacího kontroléru a testovacího agenta nebo chcete spustit test a zachytit záznam videa při jeho spuštění, je nutné nastavit agenta tak, aby běžel jako proces. Pokud přiřadíte agenty k rolím v nastaveních testu pomocí sady Visual Studio nebo přiřadíte agenty k rolím ve vašem prostředí pomocí Microsoft Test Manager, je nutné změnit nastavení pro všechny agenty přiřazené rolím, které mají pracovat s plochou.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

> [!WARNING]
> Použijete-li Microsoft Test Manager k nastavení testovacího prostředí, nainstaluje testovacího agenta. V **Průvodci vytvořením prostředí** můžete určit, že chcete nakonfigurovat jednu z rolí pro spouštění programových testů uživatelského rozhraní.

> [!IMPORTANT]
> Počítač, na kterém je spuštěn Agent, na kterém chcete spustit programové testy UI, nelze uzamknout nebo je aktivní spořič obrazovky.

Pokud používáte programové testy uživatelského rozhraní, které spouštějí prohlížeč, použije se k spuštění tohoto prohlížeče účet služby pro testovacího agenta. Tento účet služby musí být stejný jako uživatelský účet, který je aktivním uživatelem v tomto počítači. Pokud se nejedná o stejný uživatelský účet, prohlížeč se nespustí.

> [!IMPORTANT]
> Pokud používáte programový test uživatelského rozhraní, který spouští prohlížeč jako součást definice sestavení, účet služby pro službu sestavení slouží ke spuštění tohoto prohlížeče. Tento účet služby musí být stejný jako uživatelský účet, který je aktivním uživatelem v tomto počítači. Pokud se nejedná o stejný uživatelský účet, prohlížeč se nespustí.

Pomocí následujícího postupu můžete nastavit všechny agenty, kteří jsou přiřazeni k roli, která provádí úkol, který potřebuje pracovat s plochou.

## <a name="to-set-up-an-agent-to-run-as-a-process"></a>Nastavení agenta tak, aby běžel jako proces

1. Chcete-li nakonfigurovat testovacího agenta, který jste nainstalovali pro spuštění jako proces, použijte **Nástroj pro konfiguraci testovacího agenta** **Spustit** > .

   **Konfigurace testovacího agenta** se zobrazí dialogové okno.

   ![Konfigurace testovacího agenta pro Visual Studio](media/configure-test-agent.png)

2. Vyberte **interaktivní proces**. Testovací agent bude spuštěn jako proces namísto služby. Zvolte **Další**.

3. Zadejte uživatelské jméno a heslo pro uživatele, který spustí proces testovacího agenta.

   > [!NOTE]
   > - Uživatel, kterého jste přidali ke spuštění procesu, musí být také přidán jako člen skupiny TeamTestAgentService v počítači pro testovací kontrolér tohoto agenta. Pokud je tento uživatel aktuálním uživatelem, při přidání tohoto uživatele do počítače testovacího kontroléru je nutné se odhlásit nebo restartovat.
   > - Hesla s hodnotou Null nejsou pro uživatelské účty podporována.
   > - Pokud chcete používat IntelliTrace nebo data emulace sítě a diagnostický adaptér, musí být uživatelský účet členem skupiny Administrators. Pokud je v počítači, na kterém běží testovací agent, spuštěn operační systém, který má nejméně privilegovaný uživatelský účet, musíte ho spustit také jako správce (se zvýšenými oprávněními). Pokud uživatelské jméno agenta není ve službě agenta, pokusí se ho přidat, což vyžaduje oprávnění k testovacímu kontroléru.
   > - Uživatel, který se pokouší použít testovací kontrolér, musí být v účtu uživatele testovacího kontroléru nebo nebude moci spustit testy na řadiči.

4. Chcete-li zajistit, aby počítač s testovacím agentem mohl po restartování spustit testy, můžete nastavit počítač pro automatické přihlášení jako uživatel testovacího agenta. Vyberte **automatické přihlášení**. Toto uloží uživatelské jméno a heslo v zašifrované podobě v registru.

   > [!NOTE]
   > Když jste připojeni k testovacímu prostředí pomocí vzdálené plochy nebo připojení k hostům, může docházet k častým neočekávaným odpojením. Jednou z možných příčin ztráty připojení je to, že je počítač nakonfigurovaný tak, aby se automaticky přihlásil k síti.

5. Chcete-li mít jistotu, že spořič obrazovky je zakázán, protože to může narušit jakékoli automatizované testy, které musí spolupracovat s plochou, vyberte **Ujistěte se, že spořič obrazovky je zakázán**.

   > [!WARNING]
   > Pokud automatické přihlášení nebo zakázání spořiče obrazovky, vznikají bezpečnostní rizika. Povolením automatického protokolování na můžete povolit ostatním uživatelům spustit tento počítač a použít účet, který se přihlásí automaticky. Pokud zakážete spořič obrazovky, počítač nemusí vyzvat uživatele k přihlášení k odemknutí počítače. To umožňuje komukoli přístup k počítači, pokud mají fyzický přístup k počítači. Pokud povolíte tyto funkce v počítači, by měl Ujistěte se, že tyto počítače byly fyzicky zabezpečeny. Například tyto počítače jsou umístěny ve fyzicky zabezpečeném prostředí. Pokud zrušíte zaškrtnutí políčka **zkontrolovat, jestli je spořič obrazovky zakázaný**, nepovolíte spořič obrazovky.

   Chcete-li změnit agenta zpět na spuštění jako služba, můžete použít tento nástroj a vybrat **službu**.

6. Chcete-li použít změny, klikněte na tlačítko **použít nastavení**.

   Zobrazí se dialogové okno **Shrnutí konfigurace** , ve kterém se zobrazí stav jednotlivých kroků pro konfiguraci testovacího agenta.

7. Chcete-li zavřít dialogové okno **Souhrn konfigurace** , klikněte na tlačítko **Zavřít**. Pak zvolte znovu **Zavřít** a zavřete tak **Nástroj pro konfiguraci testovacího agenta**.

   > [!NOTE]
   > K dispozici je ikona oznamovací oblasti, která je spuštěna v počítači pro testovacího agenta, který je spuštěn jako proces. Zobrazuje stav testovacího agenta. Můžete spustit, zastavit nebo restartovat agenta, pokud je spuštěn jako proces, který používá tento nástroj. Chcete-li spustit testovacího agenta jako proces, pokud není spuštěn, klikněte na tlačítko **start** > **Visual Studio** > **Microsoft Visual Studio testovacího agenta**.

   Pokud je testovací kontrolér pro tohoto testovacího agenta zaregistrován ve Team Foundation Server, stav testovacího agenta, který je spuštěn jako interaktivní proces, se zobrazí v zobrazení **řadiče** v **centru testovacího prostředí** pro Microsoft Test Manager. Je uveden s předchozím symbolem hvězdičky, který označuje, že je spuštěn jako interaktivní proces. Chcete-li restartovat tohoto testovacího agenta, je nutné použít nástroj, který je spuštěn v počítači pro testovacího agenta, nikoli zobrazení **řadiče** .

## <a name="see-also"></a>Viz také:

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)
