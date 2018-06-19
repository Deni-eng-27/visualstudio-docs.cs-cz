---
title: Vyhledávání a používání rozšíření Visual Studia
ms.date: 06/07/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ExtensionManager
helpviewer_keywords:
- install extensions
- install packages
- managing extensions visual studio
ms.assetid: 4ca92d93-31b9-47ef-8109-4a429d9e2ca3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a5b562aa6fe4a64f92d66ad0a6fff0395e5314a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950277"
---
# <a name="find-and-use-visual-studio-extensions"></a>Vyhledávání a používání rozšíření Visual Studia

Rozšíření pro Visual Studio jsou kód balíčky, které běží v prostředí Visual Studio a poskytují nových nebo vylepšených funkcích nástroje Visual Studio. Můžete najít další informace o rozšíření Visual Studia zde: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Můžete použít **rozšíření a aktualizace** dialogové okno instalace rozšíření sady Visual Studio a ukázky z webů a jiných umístění a potom povolit, zakázat, aktualizovat, nebo je odinstalovat. (**Nástroje > rozšíření a aktualizace**, nebo typ **rozšíření** v **Snadné spuštění** okno). Dialogové okno také ukazuje aktualizace nainstalované ukázky a rozšíření. Můžete také stáhnout rozšíření z webů nebo je můžete získat z jiných vývojáři.

> [!NOTE]
> Spouštění v sadě Visual Studio 2015, rozšíření hostované na Visual Studio Marketplace se automaticky aktualizují. Pomocí tohoto nastavení můžete změnit **rozšíření a aktualizace** dialogové okno.  Projděte část o **automatické aktualizace rozšíření** níže podrobnosti.

## <a name="finding-visual-studio-extensions"></a>Hledání rozšíření Visual Studia

Můžete nainstalovat rozšíření z [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Rozšíření mohou být ovládací prvky, ukázky, šablony, nástroje nebo jiné součásti, které přidávají funkcionalitu do aplikace Visual Studio. Visual Studio podporuje rozšíření ve formátu balíčku VSIX – tyto zahrnují šablony projektů, šablon, položek **sada nástrojů** položek, součásti spravované rozšíření Framework (MEF) a VSPackages. Můžete také stáhnout a nainstalovat na základě MSI rozšíření, ale **rozšíření a aktualizace** nemůže povolit ani zakázat je dialogové okno. Visual Studio Marketplace obsahuje rozšíření VSIX a souboru MSI.

## <a name="installing-or-uninstalling-visual-studio-extensions"></a>Instalace nebo odinstalace rozšíření Visual Studia

V **rozšíření a aktualizace**, najít rozšíření, kterou chcete nainstalovat. (Pokud znáte název nebo část názvu rozšíření, můžete hledat v **vyhledávání** okno.) Klikněte na tlačítko **Stáhnout**.  Rozšíření se naplánuje pro instalaci. Rozšíření se nainstaluje, když jsou uzavřeny všechny instance sady Visual Studio.

Pokud se pokusíte nainstalovat rozšíření, která obsahuje závislosti, instalační služba zkontroluje, zda jsou již tyto závislosti nainstalovány. Pokud nejsou nainstalovány, **rozšíření a aktualizace** dialogové okno uvádí závislosti, které je třeba nainstalovat před instalací rozšíření.

Pokud chcete přestat používat rozšíření, lze jej zakázat nebo odinstalovat. Zakázáním rozšíření zůstane rozšíření nainstalováno, ale nedojde k jeho načtení. Můžete zakázat pouze VSIX rozšíření; rozšíření, které jsou nainstalované s použitím souboru MSI lze pouze odinstalovat. Najít rozšíření a klikněte na tlačítko **odinstalace** nebo **zakázat**. Chcete-li uvolnit zakázané rozšíření, musíte restartovat Visual Studio.

## <a name="per-user-and-administrative-extensions"></a>Na uživatele a správu rozšíření

Většina rozšíření jsou rozšíření na uživatele a jsou nainstalovány ve *%LocalAppData%\Microsoft\VisualStudio\\< verze sady Visual Studio\>\Extensions\\*  složky. Několik rozšíření jsou pro správu rozšíření a jsou nainstalovány ve *\<instalační složka nástroje Visual Studio > \Common7\IDE\Extensions\\* složky.

Abychom mohli chránit váš systém proti rozšíření, která může obsahovat chyby nebo škodlivý kód, můžete omezit uživatelská rozšíření načíst jenom v případě, že spuštění sady Visual Studio s normální uživatelské oprávnění. To znamená, že uživatelská rozšíření zakázáno při spuštění sady Visual Studio s oprávněními správce. Chcete-li to provést, přejděte na **rozšíření a aktualizace** stránka Možnosti (**nástroje > Možnosti** > **prostředí** > **rozšíření a aktualizace**, nebo stačí zadat **rozšíření** v **Snadné spuštění** okno). Vymazat **zatížení na rozšíření uživatele při spuštění jako správce** zaškrtněte políčko a potom restartujte Visual Studio.

## <a name="automatic-extension-updates"></a>Aktualizace automatické rozšíření

Rozšíření na uživatele se automaticky aktualizují, pokud je k dispozici pro Visual Studio Marketplace nové verze.  Rozpoznán a nainstalován na pozadí a v dalším restartování sady Visual Studio novou verzi rozšíření, budou používat novou verzi rozšíření.

Pouze na uživatele rozšíření lze aktualizovat automaticky.  Správce rozšíření, které jsou nainstalovány pro všechny uživatele se nebude aktualizovat a ručně nainstalujte nové verze prostřednictvím **rozšíření a aktualizace** dialogovém okně **aktualizace** uzlu. Uvidíte, které přípony bude automaticky aktualizován v podokně Podrobnosti rozšíření **rozšíření a aktualizace** dialogové okno.

Pokud chcete vypnout automatické aktualizace, můžete zakázat funkci pro všechna rozšíření a pouze konkrétní rozšíření.

- Chcete-li zakázat automatické aktualizace pro všechna rozšíření, zvolte **rozšíření a aktualizace nastavení změnit** odkaz v **rozšíření a aktualizace** dialogové okno a zrušte zaškrtnutí políčka **automaticky aktualizovat rozšíření**.

- Zakázat automatické aktualizace pro konkrétní příponu, zrušte zaškrtnutí políčka **automaticky aktualizovat toto rozšíření** možnosti v podokně podrobností rozšíření na pravé straně **rozšíření a aktualizace** dialogové okno.

> [!NOTE]
> Od verze Visual Studio 2015 Update 2, můžete zadat (v **nástroje > Možnosti > prostředí > rozšíření a aktualizace**) tom, zda má funkce Automatické aktualizace pro rozšíření na uživatele, všechna rozšíření uživatele nebo oba (výchozí nastavení nastavení).

## <a name="extension-crashunresponsiveness-notifications"></a>Rozšíření havárie nebo absence reagování oznámení

Novinka v **Visual Studio 2017 verze 15.3**, Visual Studio vás upozorní, pokud má podezření, že rozšíření byl součástí havárie v předchozí relaci. Když Visual Studio dojde k chybě, ukládá zásobník výjimek. Při příštím spuštění Visual Studio zkontroluje zásobníku, počínaje listu a směřování ve znalostní bázi. Pokud Visual Studio zjistí, že rámeček patří do modul, který je součástí nainstalované a povolené rozšíření, zobrazí oznámení.

Novinka v **Visual Studio 2017 verze 15,6 operací**, Visual Studio také vás upozorní, pokud se má podezření, že rozšíření způsobuje Uživatelském rozhraní přestal reagovat.

Když tato oznámení se zobrazují, můžete ignorovat oznámení nebo provést jednu z následujících akcí:

- Zvolte **zakáže toto rozšíření**. Visual Studio zakáže rozšíření a umožňuje vědět, jestli je potřeba restartovat systém pro zakázání vstoupily v platnost. Můžete je znovu povolit rozšíření v **rozšíření a aktualizace** dialogové, pokud chcete.

- Zvolte **tuto zprávu již nezobrazovat**.
  - Pokud oznámení týká havárie v předchozí relace, Visual Studio nebude zobrazovat, že probíhá oznámení, když se havárie spojené s touto příponou. Visual Studio, bude mít oznámení po absence reagování můžou být spojené s touto příponou, nebo dojde k chybě nebo absence reagování, který může být přidružen další rozšíření.
  - Pokud oznámení týká absence reagování, rozhraní IDE už zobrazit oznámení, když toto rozšíření je přidružen absence reagování. Visual Studio, bude mít související s havárií oznámení pro tuto příponu a související s havárií a absence reagování oznámení pro ostatní rozšíření.

- Zvolte **Další** na této stránce.

- Vyberte **X** tlačítko na konci oznámení zavření oznámení. Nové oznámení se zobrazí pro budoucí instance rozšíření bylo možné přidružit havárie nebo absence reagování uživatelského rozhraní.

> [!NOTE]
> Uživatelské rozhraní absence reagování nebo havárie oznámení znamená pouze jeden z modulů rozšíření v zásobníku se při reagovat uživatelského rozhraní, nebo pokud došlo k havárii. Je však nemusí znamenat, že rozšíření samotné bylo který. Je možné, že rozšíření volat kód, který je součástí sady Visual Studio, který naopak výsledkem reagovat uživatelského rozhraní nebo havárie. Však oznámení může být stále užitečné, pokud rozšíření, která vedla k absence reagování uživatelského rozhraní nebo havárie není pro vás důležité. V takovém případě zakázání rozšíření zabraňuje absence reagování uživatelského rozhraní nebo havárii v budoucnu, bez dopadu na produktivitu.

## <a name="sample-master-copies-and-working-copies"></a>Ukázka hlavní kopie a pracovní kopie

Při instalaci online ukázky je řešení uloženo na dvou místech:

- Pracovní kopie je uložen v umístění, které jste zadali v **nový projekt** dialogové okno.

- Samostatná hlavní kopie je uložena v počítači.

Můžete použít **rozšíření a aktualizace** dialogové okno k provedení těchto úloh souvisejících s ukázky:

- Zobrazit seznam hlavních kopií ukázek, které jste nainstalovali.

- Zakázat nebo odinstalovat hlavní kopii ukázky.

- Instalovat balíky ukázek, což jsou kolekce ukázek, které se týkají technologie nebo funkce.

- Nainstalujte jednotlivé online ukázky. (Můžete to provést taky **nový projekt** dialogové okno.)

- Zobrazit upozornění na aktualizace při zveřejnění změny zdrojového kódu nainstalovaných ukázek.

- Aktualizujte hlavní kopii nainstalované ukázka po oznámení o aktualizaci.

## <a name="installing-without-using-the-extensions-and-updates-dialog-box"></a>Instalace bez použití dialogové okno rozšíření a aktualizace

Rozšíření, která byla součástí *VSIX* soubory mohou být k dispozici v umístění než Visual Studio Marketplace. **Rozšíření a aktualizace** dialogové okno se nepodařilo zjistit tyto soubory však můžete nainstalovat *VSIX* souboru dvojitým kliknutím na soubor nebo soubor výběrem a stisknutím klávesy **Enter**klíč. Potom postupujte podle pokynů. Pokud je nainstalovaná rozšíření, můžete použít **rozšíření a aktualizace** dialogové okno povolit, zakázat nebo ho odinstalovat.

## <a name="extension-types-not-supported-by-the-extensions-and-updates-dialog-box"></a>Typy rozšíření nepodporuje dialogové okno rozšíření a aktualizace

Visual Studio bude dál podporovat rozšíření, které jsou nainstalované ve Microsoft Installer (MSI) ale není pomocí **rozšíření a aktualizace** dialogové okno bez úprav.

> [!TIP]
> Pokud obsahuje rozšíření na základě MSI *extension.vsixmanifest* soubor rozšíření se objeví v **rozšíření a aktualizace** dialogové okno.