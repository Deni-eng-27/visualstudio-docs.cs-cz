---
title: Vytváření aplikací ClickOnce z příkazového řádku | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d8ce0753c63f1dcc177f36149cad9789ec150ab
ms.sourcegitcommit: a124076dfd6b4e5aecda4d01984fee7b0c034745
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68787680"
---
# <a name="build-clickonce-applications-from-the-command-line"></a>Vytváření aplikací ClickOnce z příkazového řádku
V [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]nástroji můžete sestavit projekty z příkazového řádku, i když jsou vytvořeny v integrovaném vývojovém prostředí (IDE). Ve skutečnosti můžete znovu sestavit projekt vytvořený pomocí [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] nástroje v jiném počítači, který má nainstalován pouze .NET Framework. To umožňuje reprodukování sestavení pomocí automatizovaného procesu, například v centrálním vývojovém prostředí, nebo pomocí pokročilých skriptovacích technik nad rámec sestavování samotného projektu.

## <a name="use-msbuild-to-reproduce-clickonce-application-deployments"></a>Použití nástroje MSBuild k reprodukování nasazení aplikace ClickOnce
 Když vyvoláte MSBuild/target: Publish na příkazovém řádku, sdělí systému MSBuild, aby projekt sestavil a vytvořil [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci ve složce pro publikování. Jedná se o ekvivalent výběru příkazu **publikovat** v integrovaném vývojovém prostředí (IDE).

 Tento příkaz spustí nástroj *MSBuild. exe*, který je v cestě v prostředí příkazového řádku sady Visual Studio.

 "Target" je indikátorem pro MSBuild, jak zpracovat příkaz. Klíčové cíle jsou cíle "Build" a cíl "publikovat". Cíl sestavení je ekvivalentem výběru příkazu Build (nebo stisknutím klávesy F5) v integrovaném vývojovém prostředí (IDE). Pokud chcete projekt sestavit pouze, můžete to dosáhnout zadáním `msbuild`. Tento příkaz funguje, protože cíl sestavení je výchozí cíl pro všechny projekty generované [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. To znamená, že nemusíte explicitně zadat cíl sestavení. Proto je psaní `msbuild` stejná operace jako při psaní. `msbuild /target:build`

 `/target:publish` Příkaz instruuje nástroj MSBuild, aby vyvolal cíl publikování. Cíl publikování závisí na cíli sestavení. To znamená, že operace publikování je nadmnožinou operace sestavení. Například pokud jste provedli změnu některého z vašich Visual Basic nebo C# zdrojových souborů, odpovídající sestavení bude automaticky znovu sestavena operací publikování.

 Informace o generování úplného [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení pomocí nástroje příkazového řádku Mage. exe k [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoření manifestu naleznete v tématu [Návod: Ruční nasazení aplikace](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)ClickOnce.

## <a name="create-and-build-a-basic-clickonce-application-with-msbuild"></a>Vytvoření a sestavení základní aplikace ClickOnce pomocí nástroje MSBuild

#### <a name="to-create-and-publish-a-clickonce-project"></a>Vytvoření a publikování projektu ClickOnce

1. Otevřete Visual Studio a vytvořte nový projekt.

    Vyberte šablonu projektu **desktopová aplikace pro Windows** a pojmenujte projekt. `CmdLineDemo`

1. V nabídce **sestavení** klikněte na příkaz **publikovat** .

    Tento krok zajistí, že je projekt správně nakonfigurovaný pro vytvoření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace.

    Zobrazí se Průvodce publikováním.

1. V průvodci publikování klikněte na **Dokončit**.

    Visual Studio vygeneruje a zobrazí výchozí webovou stránku nazvanou *Publish. htm*.

1. Uložte projekt a poznamenejte si umístění složky, ve kterém je uložený.

   Výše uvedený postup vytvoří [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projekt, který byl poprvé publikován. Nyní můžete sestavení reprodukována mimo rozhraní IDE.

#### <a name="to-reproduce-the-build-from-the-command-line"></a>Pro reprodukování sestavení z příkazového řádku

1. Ukončete [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].

2. V nabídce **Start** systému Windows klikněte na **všechny programy**a pak **Microsoft Visual Studio**a pak **Visual Studio Tools**a příkazový **řádek Visual Studio**. To by mělo otevřít příkazový řádek v kořenové složce aktuálního uživatele.

3. V **příkazovém řádku sady Visual Studio**změňte aktuální adresář na umístění projektu, který jste právě vytvořili. Zadejte například příkaz `chdir My Documents\Visual Studio\Projects\CmdLineDemo`.

4. Chcete-li odebrat existující soubory vytvořené v "pro vytvoření a publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projektu", " `rmdir /s publish`Type.

    Tento krok je nepovinný, ale zajišťuje, že se nové soubory vytvořily v sestavení příkazového řádku.

5. Zadejte `msbuild /target:publish`.

   Výše uvedené kroky vytvoří úplné [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace v podsložce projektu s názvem **Publish**. *CmdLineDemo. Application* je [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest nasazení. Složka *cmdlinedemo_ 1.0.0.0* obsahuje soubory *CmdLineDemo. exe* a [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] *CmdLineDemo. exe. manifest*, manifest aplikace. *Setup. exe* je zaváděcí nástroj, který je ve výchozím nastavení nakonfigurován pro instalaci .NET Framework. Složka DotNetFX obsahuje distribuovatelné součásti pro .NET Framework. Toto je celá sada souborů, kterou potřebujete k nasazení aplikace přes web nebo přes UNC nebo CD/DVD.
   
> [!NOTE]
> Systém MSBuild používá možnost **PublishDir** k určení umístění pro výstup, `msbuild /t:publish /p:PublishDir="<specific location>"`například.

## <a name="publish-properties"></a>Vlastnosti publikování
 Při publikování aplikace ve výše uvedených postupech jsou následující vlastnosti vloženy do souboru projektu pomocí Průvodce publikováním. Tyto vlastnosti mají přímo vliv na [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] to, jak je aplikace vytvořená.

 V *CmdLineDemo. vbproj* / *CmdLineDemo. csproj*:

```xml
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>
<GenerateManifests>true</GenerateManifests>
<TargetZone>LocalIntranet</TargetZone>
<PublisherName>Microsoft</PublisherName>
<ProductName>CmdLineDemo</ProductName>
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>
<Install>true</Install>
<ApplicationVersion>1.0.0.*</ApplicationVersion>
<ApplicationRevision>1</ApplicationRevision>
<UpdateEnabled>true</UpdateEnabled>
<UpdateRequired>false</UpdateRequired>
<UpdateMode>Foreground</UpdateMode>
<UpdateInterval>7</UpdateInterval>
<UpdateIntervalUnits>Days</UpdateIntervalUnits>
<UpdateUrlEnabled>false</UpdateUrlEnabled>
<IsWebBootstrapper>true</IsWebBootstrapper>
<BootstrapperEnabled>true</BootstrapperEnabled>
```

 Jakoukoli z těchto vlastností můžete přepsat na příkazovém řádku bez změny samotného souboru projektu. Následující příklad vytvoří [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace bez zaváděcího nástroje:

```cmd
msbuild /target:publish /property:BootstrapperEnabled=false
```

 Vlastnosti publikování jsou ovládány [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] na stránkách vlastností **publikování**, **zabezpečení**a **podepisování** v **Návrháři projektu**. Níže je uveden popis vlastností publikování spolu s uvedením toho, jak jsou jednotlivé vlastnosti nastaveny na různých stránkách vlastností návrháře aplikace:

- `AssemblyOriginatorKeyFile`Určuje soubor klíče, který se používá k [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] podepsání manifestů aplikace. Stejný klíč lze také použít k přiřazení silného názvu sestavením. Tato vlastnost je nastavena na stránce **podepisování** v **Návrháři projektu**.

  Na stránce **zabezpečení** jsou nastaveny následující vlastnosti:

- **Povolit nastavení zabezpečení ClickOnce** určuje, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] jestli jsou vygenerované manifesty. Při počátečním vytvoření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projektu je generování manifestu ve výchozím nastavení vypnuto. Průvodce automaticky zapne tento příznak při prvním publikování.

- **TargetZone** určuje úroveň důvěryhodnosti, která se má vygenerovat do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu aplikace. Možné hodnoty jsou "Internet", "LocalIntranet" a "vlastní". Internet a LocalIntranet způsobí, že se do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu aplikace pošle výchozí nastavení oprávnění. LocalIntranet je výchozí a v podstatě znamená úplný vztah důvěryhodnosti. Vlastní určuje, že do manifestu [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace budou generována pouze oprávnění explicitně zadaná v souboru manifestu základní *aplikace.* Soubor *App. manifest* je částečný soubor manifestu, který obsahuje jenom definice informací o důvěryhodnosti. Jedná se o skrytý soubor, který se automaticky přidá do projektu při konfiguraci oprávnění na stránce **zabezpečení** .

  Na stránce **publikovat** jsou nastaveny následující vlastnosti:

- `PublishUrl`je umístění, do kterého bude aplikace publikována v integrovaném vývojovém prostředí. Je vložen do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu aplikace, pokud `InstallUrl` není zadána vlastnost nebo `UpdateUrl` .

- `ApplicationVersion`Určuje verzi [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Toto je číslo verze se čtyřmi číslicemi. Pokud je poslední číslice "*", pak `ApplicationRevision` je nahrazena hodnotou vloženou do manifestu v čase sestavení.

- `ApplicationRevision`Určuje revizi. Toto je celé číslo, které zvýší pokaždé, když publikujete v integrovaném vývojovém prostředí. Všimněte si, že se automaticky nezvyšuje pro sestavení prováděná na příkazovém řádku.

- `Install`Určuje, zda je aplikace nainstalovaná aplikace nebo aplikace spouštěná z webu.

- `InstallUrl`(nezobrazený) je umístění, ze kterého budou uživatelé aplikaci instalovat. Je-li tento parametr zadán, je tato hodnota vypálena do zaváděcího `IsWebBootstrapper` nástroje *Setup. exe* , pokud je vlastnost povolena. Je-li `UpdateUrl` zadána, je také vložen do manifestu aplikace.

- `SupportUrl`(nezobrazený) je umístění propojené v dialogovém okně **Přidat nebo odebrat programy** nainstalované aplikace.

  Následující vlastnosti jsou nastaveny v dialogovém okně **aktualizace aplikace** , ke kterým se dostanete ze stránky **publikování** .

- `UpdateEnabled`Určuje, zda má aplikace vyhledat aktualizace.

- `UpdateMode`Určuje aktualizace popředí nebo aktualizace na pozadí.

- `UpdateInterval`Určuje, jak často by měla aplikace vyhledávat aktualizace.

- `UpdateIntervalUnits`Určuje, zda `UpdateInterval` je hodnota v jednotkách hodiny, dny nebo týdny.

- `UpdateUrl`(nezobrazený) je umístění, ze kterého bude aplikace přijímat aktualizace. Je-li tento parametr zadán, je tato hodnota vložena do manifestu aplikace.

- Následující vlastnosti jsou nastaveny v dialogovém okně **Možnosti publikování** , ke kterým se dostanete ze stránky **publikování** .

- `PublisherName`Určuje název vydavatele zobrazeného na příkazovém řádku, který se zobrazí při instalaci nebo spuštění aplikace. V případě nainstalované aplikace se také používá k určení názvu složky v nabídce **Start** .

- `ProductName`Určuje název produktu zobrazený v příkazovém řádku, který se zobrazí při instalaci nebo spuštění aplikace. V případě nainstalované aplikace se také používá k zadání názvu zástupce v nabídce **Start** .

- Následující vlastnosti jsou nastaveny v dialogovém okně **předpoklady** , ke kterým se přistupoval ze stránky **publikování** .

- `BootstrapperEnabled`Určuje, zda se má generovat zaváděcí nástroj *Setup. exe* .

- `IsWebBootstrapper`Určuje, zda zaváděcí nástroj *Setup. exe* funguje na webu nebo v režimu na disku.

## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL, SupportUrl, PublishURL a UpdateURL
 V následující tabulce jsou uvedeny čtyři možnosti adresy URL pro nasazení ClickOnce.

|Možnost adresy URL|Popis|
|----------------|-----------------|
|`PublishURL`|Vyžaduje se, pokud publikujete aplikaci ClickOnce na web.|
|`InstallURL`|Volitelné. Tuto možnost adresy URL nastavte, pokud se instalační web liší od `PublishURL`. Můžete například nastavit `PublishURL` cestu k serveru FTP a `InstallURL` nastavit na adresu URL webu.|
|`SupportURL`|Volitelné. Tuto možnost adresy URL nastavte, pokud se web podpory liší od `PublishURL`. Můžete například nastavit `SupportURL` na web zákaznická podpora vaší společnosti.|
|`UpdateURL`|Volitelné. Nastavte tuto možnost adresy URL, pokud se umístění aktualizace liší od `InstallURL`. Můžete například nastavit `PublishURL` cestu k serveru FTP a `UpdateURL` nastavit na adresu URL webu.|

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.Build.Tasks.GenerateBootstrapper>
- <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>
- <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>
- [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)
- [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
