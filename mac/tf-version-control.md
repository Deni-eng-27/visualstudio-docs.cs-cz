---
title: Team Foundation Version Control (TFVC)
description: Připojení z aplikace Visual Studio pro Mac na Team Foundation serveru/Azure DevOps s Team Foundation Version Control (TFVC).
author: conceptdev
ms.author: crdun
ms.date: 04/04/2019
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 20c739057bcbded922df62ce00e1b0c7e07d9f75
ms.sourcegitcommit: aeb1a1135dd789551e15aa5124099a5fe3f0f32b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2019
ms.locfileid: "66501000"
---
# <a name="connecting-to-team-foundation-version-control"></a>Připojování k Team Foundation – správa verzí

> [!NOTE]
> Pro nejlepší výkon verze ovládacího prvku v systému macOS doporučujeme používat Git namísto Team Foundation verze ovládacího prvku (TFVC). Git je podporováno v sadě Visual Studio pro Mac a výchozí volba pro úložiště hostovaná v Team Foundation Server (TFS) nebo Azure DevOps. Další informace o používat Git na TFS/Azure DevOps, najdete v článku [nastavení úložiště Git](/visualstudio/mac/set-up-git-repository) článku.

Úložiště Azure nabízí dva modely správy verzí: [Git](/azure/devops/repos/git/?view=azure-devops), distribuovaný systém řízení verze, a [Team Foundation Version Control](/azure/devops/repos/tfvc/index?view=azure-devops) (TFVC), centralizované verze ovládacího prvku systému.

Visual Studio for Mac obsahuje plnou podporu pro úložiště Git, ale vyžaduje nějaké řešení pro práci s TFVC. Pokud používáte TFVC pro správu verzí ještě dnes, tady jsou některá řešení, které lze použít pro přístup k zdrojového kódu hostovaná v TFVC.

* [Použijte Visual Studio Code a rozšíření úložiště Azure pro grafické uživatelské rozhraní](#use-visual-studio-code-and-the-azure-repos-extension)
* [Připojení k úložišti pomocí Team Explorer Everywhere příkazového řádku klienta (TEE CLC)](#connecting-using-the-team-explorer-everywhere-command-line-client)
* [Připojte se k TFVC pomocí (nepodporované) rozšíření Team Foundation – správa verzí pro Visual Studio pro Mac](#connect-to-tfvc-using-the-team-foundation-version-control-extension)

Zbývající část tohoto článku vás provede výše uvedených možností.

## <a name="requirements"></a>Požadavky

* Visual Studio Community, Professional nebo Enterprise for Mac verze 7,8 nebo novější.
* Služby Azure DevOps, Team Foundation Server 2013 a novější, nebo v Azure DevOps Server 2018 nebo později.
* Projekt Azure DevOps Services nebo Team Foundation serveru/Azure DevOps serveru, nakonfigurovaný pro použití správy verzí Team Foundation.

## <a name="use-visual-studio-code-and-the-azure-repos-extension"></a>Pomocí Visual Studio Code a rozšíření úložiště Azure

Pokud chcete pracovat s grafické rozhraní pro správu souborů ve správě verzí, rozšíření úložiště Azure pro Visual Studio Code poskytuje podporované řešení od Microsoftu. Abyste mohli začít, stáhněte si [Visual Studio Code](https://code.visualstudio.com) a dozvíte se, jak [konfiguraci rozšíření úložiště Azure](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team).

## <a name="connecting-using-the-team-explorer-everywhere-command-line-client"></a>Připojení pomocí Team Explorer Everywhere příkazového řádku klienta

Pokud vám vyhovuje, pomocí macOS terminálu, a potom Team Explorer Everywhere klienta příkazového řádku (TEE CLC) poskytuje podporovaný způsob, jak se připojit ke zdroji v TFVC.

Provedením následujících kroků k nastavení připojení pro TFVC a změn.

Speciální díky Chris Pilcher, vývojář v naší komunitě, jehož [původní pokyny pro TEE-CLC](https://gist.github.com/chris-pilcher/a3f14eb081d7ab983e5c) vytvořený na základě této části.

### <a name="setting-up-the-tee-clc"></a>Nastavení TEE-CLC

Existují dva způsoby, jak získat instalačnímu programu TEE – certifikát pro vystavování licencí.

* Použijte Homebrew k instalaci klienta, nebo
* Stáhněte si a ruční instalaci klienta

Nejjednodušším řešením je **pomocí HomeBrew**, což je Správce balíčků pro macOS. Chcete-li nainstalovat pomocí této metody:

1. Spusťte terminálu aplikace pro macOS.
1. Nainstalujte Homebrew na pomocí terminálu a podle pokynů [Homebrew domovskou stránku](https://brew.sh/).
1. Po instalaci Homebrew, v terminálu spusťte následující příkaz: `brew install tee-clc`

K **ručně nastavit TEE-CLC**:

1. [Stáhněte si nejnovější verzi tee-clc](https://github.com/Microsoft/team-explorer-everywhere/releases) z stránku vydané verze Team Explorer Everywhere úložiště GitHub (například tee-clc-14.134.0.zip v době psaní tohoto textu).
1. Extrahujte obsah .zip do složky na disku.
1. Otevřete aplikaci terminál macOS a použít `cd` příkaz pro přepnutí do složky, které jste použili v předchozím kroku.
1. Ze složky, spusťte příkaz `./tf` otestovat, lze spustit klienta příkazového řádku, můžete být vyzváni k instalaci Javy nebo další závislosti.

Po instalaci TEE-CLC můžete spustit příkaz `tf eula` k zobrazení a přijměte licenční smlouvu pro klienta.

A konečně k ověření s vaším prostředím TFS/Azure DevOps, bude potřeba vytvořit osobní přístupový token na serveru. Další informace o [dvojúrovňovém osobní přístupové tokeny](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/pats?view=azure-devops). Při vytváření osobního přístupového tokenu pro použití s TFVC, ujistěte se, že jste při konfiguraci token poskytnout úplný přístup.

### <a name="using-the-tee-clc-to-connect-to-your-repo"></a>Pomocí TEE-CLC k připojení k úložišti

Chcete-li se připojit ke zdrojovému kódu, musíte nejprve vytvořit pracovní prostor pomocí `tf workspace` příkazu. Například následující příkazy připojit k organizaci v Azure DevOps služby s názvem "TatoOrganizace": 

```bash
export TF_AUTO_SAVE_CREDENTIALS=1
tf workspace -new MyWorkspace -collection:https://dev.azure.com/MyOrganization
```

`TF_AUTO_SAVE_CREDENTIALS` Nastavení prostředí, které se používá k uložení svých přihlašovacích údajů, zobrazí se výzva k zadání je více než jednou. Po zobrazení výzvy k zadání uživatelského jména použijte osobní přístupový token, který jste vytvořili v předchozí části a heslo necháte prázdné.

Nyní, pokud chcete vytvořit mapování zdrojových souborů do místní složky, budete používat `tf workfold` příkazu. Následující příklad provede mapování složky s názvem "WebApp.Services" z "MyRepository" TFVC projekt a nastavit tak, aby je možné zkopírovat do složky místní ~/Projects/ (to znamená "Projekty" složku v aktuální uživatel domovskou složku).

```bash
tf workfold -map $/MyRepository/WebApp.Services -workspace:MyWorkspace ~/Projects/
```

Nakonec použijte následující příkaz k získání zdrojové soubory ze serveru a místní kopírování:

```bash
tf get
```

### <a name="committing-changes-using-the-tee-clc"></a>Potvrzují se změny pomocí TEE-CLC

Po provedení změny na soubory v sadě Visual Studio pro Mac, můžete přepnout zpět do terminálu k vrácení se změnami úpravy. `tf add` Příkaz slouží k přidání souborů do seznamu čekajících změn se zrušenou registrací a `tf checkin` příkaz provede skutečné vrácení se změnami na server. `checkin` Příkaz obsahuje parametry pro přidání komentáře nebo přidružit související pracovní položky. V následujícím fragmentu kódu, všechny soubory `WebApp.Services` složky jsou přidány, rekurzivně, k vrácení se změnami. Kód je pak navázalo kontakt se komentář a přidružené pracovní položky s ID "42".

```bash
cd WebApp.Services
tf add * /recursive
tf checkin -comment:"Replaced 'Northwand' typos with the correct word Northwind" -associate:42
```

Další informace o příkazy popsané zde, nebo jiné, můžete pomocí následujícího příkazu z terminálu:

`tf help`

## <a name="connect-to-tfvc-using-the-team-foundation-version-control-extension"></a>Připojte se k rozšíření Team Foundation – správa verzí pomocí TFVC

> [!NOTE]
> Pro nejlepší výkon verze ovládacího prvku v systému macOS doporučujeme používat Git namísto Team Foundation verze ovládacího prvku (TFVC). Git je podporováno v sadě Visual Studio pro Mac a výchozí volba pro úložiště hostovaná v Team Foundation Server (TFS) nebo Azure DevOps. Další informace o používat Git na TFS/Azure DevOps, najdete v článku [nastavení úložiště Git](/visualstudio/mac/set-up-git-repository) článku.

V sadě Visual Studio pro Mac rozšíření Galerie je rozšíření pro ovládací prvky verzí produktu Team Foundation, která nabízí omezenou podporu pro připojení k TFVC. Rozšíření není podporovaný a má několik známých problémů, takže vaše zkušenosti mohou lišit v závislosti na jeho použití.

Chcete-li nainstalovat rozšíření, spusťte sadu Visual Studio pro Mac a zvolte **sady Visual Studio > rozšíření** nabídky. V **Galerie** kartu, vyberte možnost **verzí > správy verzí Team Foundation serveru TFS a Azure DevOps** a klikněte na tlačítko **instalace...** :

![Správce rozšíření](media/tfvc-install.png)

Postupujte podle pokynů k instalaci rozšíření. Po instalaci ji restartujte integrované vývojové prostředí.

### <a name="updating-the-extension"></a>Aktualizuje se rozšíření

Aktualizace rozšíření TFVC probíhají pravidelně. Přístup k aktualizace, zvolte **sady Visual Studio > rozšíření...**  z nabídky a vybereme **aktualizace** kartu. Vyberte požadované rozšíření v seznamu a stisknutím klávesy **aktualizace** tlačítka:

Stisknutím klávesy **nainstalovat** v dalším dialogovém okně starý balíček odinstalovat a nainstalovat nové.

### <a name="using-the-extension"></a>Pomocí rozšíření

Po instalaci rozšíření, vyberte **verzí > TFS/Azure DevOps > Otevřít ze vzdáleného úložiště...**  položky nabídky.

![Položka nabídky otevřít rozšíření](media/tfvc-source-control-explorer-devops.png)

Zvolte buď VSTS nebo Team Foundation Server, a začít pracovat se stisknutím klávesy **pokračovat**:

![Připojení k serveru](media/tfvc-choose-server-type-devops.png)

#### <a name="azure-repos-authentication"></a>Ověřování Azure úložišť

Když vyberete projekt, který je hostitelem úložiště Azure, budete vyzváni k zadání podrobnosti o vašem účtu Microsoft:

![Spojte se s Azure úložišť](media/tfvc-vsts-login.png)

#### <a name="tfs-authentication"></a>Ověřování serveru TFS

Pro připojení k TFS, zadejte podrobnosti o serveru a přihlašovací údaje účtu. Zadejte doménu na použití ověřování NTLM, jinak nechejte pole prázdné, použije se základní ověřování. Vyberte **přidat Server**:

![Přihlaste se k serveru TFS](media/tfvc-login.png)

### <a name="selecting-a-project"></a>Výběr projektu

Jakmile byli jste úspěšně ověřeni, zobrazí se seznam úložišť, které jsou přidružené k účtu v **otevřít ze správy zdrojových kódů** dialogové okno:

![Otevřít ze správy zdrojových kódů dialogové okno s projekty, zobrazí](media/tfvc-vsts-projects.png)

Toto dialogové okno je uspořádaný s následující uzly:

- Azure DevOps organizace nebo kolekci – zobrazí se všechny organizace, které jsou připojené k účtu Microsoft, který jste přihlášení.
- Projekty – v každé organizaci nebo kolekci, může mít celou řadou projektů. Projekt je, kde jsou hostované zdrojový kód, pracovní položky a automatizované sestavování.

V tomto okamžiku můžete vyhledávat a filtrovat podle názvu projektu nebo organizace.

#### <a name="adding-a-new-server"></a>Přidání nového serveru

Chcete-li přidat nový server do seznamu, stiskněte **přidat hostitele** tlačítko **otevřít ze správy zdrojových kódů** dialogové okno:

![Zvýrazní tlačítko pro přidání nového serveru do seznamu přidat](media/tfvc-add-new-server.png)

Vyberte poskytovatele ze seznamu a zadejte svoje přihlašovací údaje:

![Dialogové okno zobrazující možnost pro poskytovatele správy zdrojového kódu](media/tfvc-add-new-creds-devops.png)

### <a name="creating-a-new-workspace"></a>Vytváří se nový pracovní prostor

Pokud chcete začít pracovat s projektem, budete muset mít _pracovní prostor_. Pokud ještě nemáte pracovní prostor, můžete vytvořit jeden z **pracovní prostor** – pole se seznamem v **otevřít ze správy zdrojových kódů** dialogové okno:

![Vytvořit nový pracovní prostor – pole se seznamem možností](media/tfvc-create-new-workspace.png)

Nastavte název a místní cestu k novému pracovnímu prostoru a vyberte **vytvořit pracovní prostor**:

![Zadat místní cestu a název nového pracovního prostoru](media/tfvc-local-workspace.png)

### <a name="using-the-source-code-explorer"></a>Pomocí Průzkumníka zdrojového kódu

Po vytvoření pracovního prostoru a mapována do projektu, můžete začít pracovat s _Průzkumník zdrojového kódu_.

Otevřít Průzkumníka zdrojového kódu, vyberte **verzí > TFS/Azure DevOps > Průzkumník správy zdrojového kódu** položky nabídky.

Průzkumník zdrojového kódu umožňuje procházet z namapované projekty, jejich soubory a složky. Také umožňuje provádět všechny akce správy základní zdrojů, jako:

- Získat nejnovější verzi
- Získání určité verze
- Rezervace souborů a vrácení souborů se změnami
- Zamknutí a odemknutí soubory
- Přidání, odstranění a přejmenování souborů
- Zobrazit historii
- Porovnejte změny.

Mnohé z těchto akcí jsou k dispozici prostřednictvím kontextu akce na projekt:

![Místní nabídka Akce pro projekt](media/tfvc-sourcecode-actions.png)

### <a name="managing-workspaces"></a>Správa pracovních prostorů

Pokud jste ještě nevytvořili pracovního prostoru, jak je popsáno v [vytvoření pracovního prostoru](#creating-a-new-workspace) oddílu, můžete si všimnout, že je prázdný Průzkumník zdrojového kódu:

![prázdný zdrojový kód explorer](media/tfvc-setup-empty-sce.png)

Nastavení vzdáleného projekt pomocí místního pracovního prostoru, postupujte následovně:

1. Vyberte **Server** z pole se seznamem.
1. Mějte na paměti, že neexistují "žádné pracovní prostory" a zda je místní cesta "Nenamapované". Vyberte **nenamapované** odkazu zobrazíte **vytvořit nový pracovní prostor** dialogového okna.
1. Zadejte název pracovního prostoru a potom klikněte na tlačítko **pracovní složka** mapování projektu do místní složky v počítači:

    ![Vytvořit nový pracovní prostor dialog s informací, výchozí možnosti](media/tfvc-workspace1.png)

1. Vyberte složky "$" do všech projektů na serveru mapují na stejný pracovní prostor, nebo vyberte jednotlivé projekt a klikněte na tlačítko **OK**:

    ![Procházet pro složku dialogové okno zobrazující všechny projekty](media/tfvc-workspace2.png)

1. Vyberte umístění na místním počítači, který chcete namapovat projekt(y) na tento a klikněte na tlačítko **vybrat složku**.
1. Zkontrolujte podrobnosti o nový pracovní prostor stisknutím kombinace kláves **OK**

    ![Vytvořit dialogové okno Nový pracovní prostor se přidá pracovní složky](media/tfvc-workspace3.png)

Po nastavení pracovního prostoru lze změnit nebo odebrat po kliknutí **spravovat pracovní prostory** tlačítko v Průzkumníku zdrojového kódu.

![Správa pracovních prostorů](media/tfvc-workspace4.png)

## <a name="troubleshooting-and-known-issues"></a>Řešení potíží a známé problémy

#### <a name="problems-using-basic-authentication"></a>Potíže při použití základního ověřování

Tyto možnosti lze použít k ověření serveru:

- OAuth
- Základní
- Ntlm

Základní ověřování je nutná pro povolení **přihlašovací údaje pro alternativní ověření** ve službách Azure DevOps, pomocí následujících kroků:

1. Přihlaste se k vaší organizaci Azure DevOps jako vlastník (protokol https:\//dev.azure.com/{organization}/{project}).

2. Z panelu nástrojů organizace, vyberte ikonu ozubeného kola a vyberte **zásady**:

    ![Vybraná možnost nastavení zásad](media/tfvc-auth2.png)

3. Zkontrolujte nastavení připojení k aplikaci. Změna těchto nastavení v závislosti na vašich zásadách zabezpečení:

    ![Vybraná možnost nastavení zásad](media/tfvc-auth.png)

#### <a name="i-do-not-see-anything-in-tfvc"></a>Nevidím v TFVC nic

Nastavit si Team Foundation verze ovládacího prvku (TFVC) ve vašem vývojovém počítači můžete **musí** vytvořit pracovní prostor, jak je popsáno v [Správa pracovních prostorů](#managing-workspaces) oddílu.

V Průzkumníku správy zdrojového kódu, stiskněte **spravovat pracovní prostory** tlačítko. Postupujte podle kroků pro mapování projektu do složky na svém vývojovém počítači.

#### <a name="i-do-not-see-any--all-of-my-projects"></a>Nevidím žádné / all Moje projekty

Po ověření, měli byste vidět seznam projektů. Ve výchozím nastavení jsou uvedeny pouze projekty TFS. Pokud chcete zobrazit jiné typy projektů, zaškrtněte políčko "«Zobrazit všechny projekty".

Mějte na paměti, že projekty, které jsou na serveru se nezobrazí, pokud nemáte dostatečná oprávnění.

##### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>Dochází k chybě "nejde vytvořit pracovní prostor. Zkuste to prosím znovu"

Při pokusu o [vytvořit nový pracovní prostor](#creating-a-new-workspace), se ujistěte, že jsou splněny následující podmínky:

- Zákaz použití neplatné znaky v názvu pracovního prostoru.
- Název musí být menší než 64 znaků.
- Místní cesta nemůže využívat ostatní pracovní prostory.

### <a name="see-also"></a>Viz také:

- [Vývoj a sdílení kódu v TFVC pomocí sady Visual Studio (Windows)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)