---
title: Přidání odkazů v správce odkazů
ms.date: 04/11/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ReferenceManager
helpviewer_keywords:
- C# projects, references
- references [Visual Studio], adding
- assemblies [Visual Studio], references
- Visual Basic projects, references
- project references, adding
- referencing components, adding references
- project references, removing
- referencing assemblies
- referencing components, removing references
- references [Visual Studio], removing
- referencing components, assemblies not listed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33b9b29cef4ad215e76af57e66c73eb2e8a134db
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31953833"
---
# <a name="how-to-add-or-remove-references-by-using-the-reference-manager"></a>Postupy: Přidání nebo odebrání odkazů pomocí Správce odkazů

Můžete použít **správce odkazů** dialogové okno pro přidání a správa odkazuje součásti, které jste společnosti Microsoft, nebo vyvinuté jiné společnosti. Pokud vyvíjíte aplikace pro Universal Windows, projekt všechny správné knihoven DLL Windows SDK automaticky odkazuje. Pokud vyvíjíte aplikaci .NET, projekt automaticky odkazuje *mscorlib.dll*. Některé rozhraní API technologie .NET jsou zveřejněné v součásti, které budete muset přidat ručně. Odkazy na komponenty modelu COM nebo vlastní součásti nutné přidat ručně.

## <a name="reference-manager-dialog-box"></a>Dialogové okno Správce odkazů

**Správce odkazů** dialogové okno zobrazí různých kategorií na levé straně, v závislosti na typu projektu:

- **Sestavení**, s **Framework** a **rozšíření** podskupiny.

- **COM**, obsahuje všechny komponenty modelu COM, které jsou k dispozici pro odkazování.

- **Řešení**, s **projekty** podskupinu.

- **Windows**, s **základní** a **rozšíření** podskupiny. Odkazy ve Windows SDK nebo rozšíření sady SDK můžete prozkoumat pomocí **Prohlížeč objektů**.

- **Procházet**, s **poslední** podskupinu.

## <a name="add-and-remove-a-reference"></a>Přidání a odebrání odkazu

### <a name="to-add-a-reference"></a>Přidání odkazu

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na **odkazy** nebo **závislosti** uzel a zvolte **přidat odkaz na**. Můžete také kliknout pravým tlačítkem na uzel projektu a vyberte **přidat** > **odkaz**.

   **Správce odkazů** k otevření a odkazy na dostupné skupinou.

2. Zadejte odkazy na Přidat a pak vyberte **OK**.

## <a name="assemblies-tab"></a>Karta Sestavení

**Sestavení** karta Vypíše seznam všech sestavení rozhraní .NET Framework, které jsou k dispozici pro odkazování. **Sestavení** karta nemá seznam žádné sestavení z globální mezipaměti sestavení (GAC), protože sestavení v mezipaměti GAC jsou součástí běhové prostředí. Pokud nasazení nebo zkopírujte aplikaci, která obsahuje odkaz na sestavení, který je zaregistrován v mezipaměti GAC, sestavení nebude nasazen nebo zkopírovat s aplikací, bez ohledu na to **místní kopie** nastavení. Další informace najdete v tématu [Správa odkazů v projektu](../ide/managing-references-in-a-project.md).

Když ručně přidejte odkaz na všechny obory názvů EnvDTE (<xref:EnvDTE>, <xref:EnvDTE80>, <xref:EnvDTE90>, <xref:EnvDTE90a>, nebo <xref:EnvDTE100>), můžete nastavit **vložit zprostředkovatel komunikace s objekty typy** vlastnost odkazu na **False** v **vlastnosti** okno. Nastavení této vlastnosti na **True** můžete příčina vytvořit z důvodu některé EnvDTE vlastnosti, která nelze vložit problémy.

Všechny plochy projekty obsahují implicitní odkaz na **mscorlib**. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty obsahují implicitní odkaz na <xref:Microsoft.VisualBasic>. Všechny projekty obsahují implicitní odkaz na **System.Core**i v případě, že se odebere ze seznamu odkazů.

Pokud typ projektu nepodporuje sestavení, na kartě se nebude zobrazovat na **správce odkazů** dialogové okno.

**Sestavení** karta se skládá z dvě dílčí karty:

1. **Framework** uvádí všechna sestavení, které tvoří cílové rozhraní.

    Projekty pro aplikace pro Windows 8.x Store obsahovat odkazy na všechna sestavení v cílovou [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] ve výchozím nastavení při vytváření projektu. Spravované projektů, pod uzlem jen pro čtení **odkazy** složky v **Průzkumníku řešení** označuje odkaz na celý framework. Podle toho **Framework** nebude výčet některý z těchto sestavení z rozhraní a místo toho zobrazí se následující zpráva: "všechna sestavení Framework se už neodkazuje. Použijte prohlížeč objektů a prozkoumejte odkazy v rozhraní Framework." Pro stolní projekty **Framework** karta zobrazí sestavení z cílové rozhraní, a uživatel musí přidat odkazy, které aplikace vyžaduje.

2. **Rozšíření** uvádí všechna sestavení, která externích dodavatelů součásti a ovládacích prvků vyvinuly rozšířit cílové rozhraní. Podle účelu dané aplikace mohou být tato sestavení potřebná.

   **Rozšíření** nebude naplněn sadou vytváření výčtu sestavení, které jsou zaregistrovány v následujících umístěních:

   32bitový počítač:
   - `HKEY_CURRENT_USER\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]`
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]`

   64bitový počítač:
   - `HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]`
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]`

   A starší verze [cílový Framework identifikátor]

   Pokud projekt cílem rozhraní .NET Framework 4 na 32bitový počítač, například **rozšíření** projde sestavení, které jsou zaregistrovány v rámci *\Microsoft\.NETFramework\v4.0\AssemblyFoldersEx*, *\Microsoft\.NETFramework\v3.5\AssemblyFoldersEx*, *\Microsoft\.NETFramework\v3.0\AssemblyFoldersEx*, a  *\Microsoft\.NETFramework\v2.0\AssemblyFoldersEx*.

Některé součásti v seznamu nemusí být zobrazeny v závislosti na verzi rozhraní .NET Framework projektu. Tato situace může nastat za následujících podmínek:

- Komponenta, která používá nejnovější verzi rozhraní .NET Framework je nekompatibilní s projektu, jehož cílem dřívější verzi rozhraní .NET Framework.

    Informace o tom, jak změnit cílová verze rozhraní .NET Framework pro projekt najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

- Komponenta, která používá [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] není kompatibilní s projektu, jehož cílem [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)].

    Když vytvoříte novou aplikaci, některé cílové projekty [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] ve výchozím nastavení.

- Neměli byste přidávání odkazů na soubor do jiného projektu výstupy ve stejném řešení, protože to může způsobit chyby kompilace. Místo toho použijte **projekty** kartě **přidat odkaz na** dialogové okno vytvořit odkazy na projekt na projekt. To usnadňuje vývoj v týmu tím, že umožňuje lepší správu knihovny tříd, které vytvoříte ve vašich projektů. Další informace najdete v tématu [Poradce při potížích přerušený odkazy](../ide/troubleshooting-broken-references.md).

> [!NOTE]
> V sadě Visual Studio 2015 nebo novější je vytvořen odkaz na soubor místo odkaz na projekt, pokud cílová verze rozhraní .NET Framework jeden projektu je verze 4.5 nebo novější, a cílovou verzi sady jiný projekt je verze 2, 3, 3.5 nebo 4.0.

### <a name="to-display-an-assembly-in-the-add-reference-dialog-box"></a>Chcete-li zobrazit v dialogovém okně Přidat odkaz na sestavení

- Přesuňte nebo zkopírujte sestavení do jednoho z následujících umístění:

    - Aktuální adresář projektu. (Tyto sestavení můžete najít pomocí **Procházet** karta.)

    - Další adresáře projektu ve stejném řešení. (Tyto sestavení můžete najít pomocí **projekty** karta.)

    \- nebo –

- Nastavte klíč registru, který určuje umístění sestavení, které chcete zobrazit:

   Pro 32bitový operační systém přidejte jedno z následujících klíčů registru.

   - `[HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework\<VersionMinimum>\AssemblyFoldersEx\MyAssemblies]@="<AssemblyLocation>"`

   - `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\<VersionMinimum>\AssemblyFoldersEx\MyAssemblies]@="<AssemblyLocation>"`

   Pro 64bitový operační systém přidejte jedno z těchto klíčů registru v podregistru 32bitového registru.

   - `[HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\<VersionMinimum>\AssemblyFoldersEx\MyAssemblies]@="<AssemblyLocation>"`

   - `[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\<VersionMinimum>\AssemblyFoldersEx\MyAssemblies]@="<AssemblyLocation>"`

   *\<VersionMinimum\>*  je nejnižší verze rozhraní .NET Framework, která se použije. Pokud *\<VersionMinimum\>* je v3.0, složky zadané v *AssemblyFoldersEx* použít projektů cílených na rozhraní .NET Framework 3.0 a novějších.

   *\<AssemblyLocation\>*  je sestavení, která se má zobrazit v adresáři **přidat odkaz na** dialogové okno, například *C:\MyAssemblies*.

   Vytvoření klíče registru pod `HKEY_LOCAL_MACHINE` uzel umožňuje všem uživatelům zobrazit sestavení v zadaném umístění v **přidat odkaz na** dialogové okno. Vytvoření klíče registru pod `HKEY_CURRENT_USER` uzel ovlivňuje pouze nastavení pro aktuálního uživatele.

   Otevřete **přidat odkaz na** dialogové okno znovu. Sestavení by se měla objevit na **.NET** kartě. Pokud ne, ujistěte se, že sestavení jsou umístěny v zadané *AssemblyLocation* adresáře, restartujte Visual Studio a akci opakujte.

## <a name="projects-tab"></a>Karta projekty

**Projekty** karta Vypíše seznam všech kompatibilní projekty v řešení bude aktuální v **řešení** dílčí karty.

Projekt může odkazovat na jiný projekt, který cílí na jinou verzi rozhraní .NET Framework. Například můžete vytvořit projektu s cílem [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] , ale který odkazuje na sestavení, které se sestavily pro rozhraní .NET Framework 2. Však nemůže odkazovat na rozhraní .NET Framework 2 projektu [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] projektu. Další informace najdete v tématu [přehled cílení na více](../ide/visual-studio-multi-targeting-overview.md).

Projektu, jehož cílem [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] není kompatibilní s projektu, jehož cílem [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].

Odkaz na soubor se vytvoří místo odkaz na projekt, pokud jeden projektu cílí na rozhraní .NET Framework 4 a jiného projektu zaměřuje na starší verzi.

Projektu, jehož cílem [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] nelze přidat odkaz na projekt do projektu, jehož cílem rozhraní .NET Framework a naopak.

## <a name="windows-tab"></a>Karta Windows

**Windows** karta Vypíše seznam všech sad SDK, které jsou specifické pro platformy, které operační systémy Windows spustit.

Soubor WinMD je možné v sadě Visual Studio vygenerovat dvěma způsoby:

- **Spravované aplikace pro Windows 8.x Store projekty**: projekty pro Windows 8.x Store aplikace můžete výstup WinMD binárních souborů nastavením **vlastnosti projektu** > **výstupní typ = souboru WinMD**. Název souboru WinMD musí představovat nadřazený obor názvů všech oborů názvů, které existují jeho v rámci. Například, pokud projektu se skládá z oborů názvů `A.B` a `A.B.C`, jsou možné názvy pro jeho outputted WinMD *A.winmd* a *A.B.winmd*. Pokud uživatel zadá **vlastnosti projektu** > **název sestavení** nebo **vlastnosti projektu** > **Namespace**hodnotu, která je nesouvislý ze sady obory názvů v projektu nebo je nadmnožinou obor názvů v rámci projektu, se generuje upozornění sestavení: "'A.winmd' není platný .winmd název souboru pro toto sestavení." Všechny typy v rámci souboru metadat systému Windows musejí existovat v podřízeném oboru názvů daného názvu souboru. Typy, které nejsou v oboru názvů sub názvu souboru, nebudete moci být umístěné za běhu. V tomto sestavení je nejmenší společný obor názvů `CSWSClassLibrary1`. Plocha jazyka Visual Basic nebo projektu C# můžete jenom využívat WinMDs, který je vytvořen pomocí sady Windows 8 SDK, což se označuje jako první strany WinMDs, a nelze generovat WinMDs.

- **Nativní projekty pro Windows 8.x Store aplikace**: nativní WinMD soubor obsahuje pouze metadata. Jeho implementace se nachází v samostatném souboru knihovny DLL. Jeden může vytvářet nativní binární soubory výběrem šablony projektu komponenty prostředí Windows Runtime **nový projekt** dialogové okno nebo spuštěním z prázdného projektu a změna vlastností projektu pro generování souboru WinMD. Pokud projekt obsahuje nesouvislé obory názvů, chyba sestavení oznámí uživateli, aby sloučit své obory názvů nebo spustit nástroj MSMerge.

**Windows** karta se skládá ze dvou podskupiny.

### <a name="core-subgroup"></a>Základní podskupinu

**Základní** podskupinu zobrazí seznam všech WinMDs (pro prvky prostředí Windows Runtime) v sadě SDK pro cílovou verzi systému Windows.

Projekty pro Windows 8.x Store aplikace obsahovat odkazy na všechny WinMDs ve Windows 8 SDK ve výchozím nastavení při vytváření projektu. Spravované projektů, pod uzlem jen pro čtení **odkazy** složky v **Průzkumníku řešení** označuje odkaz na celý Windows 8 SDK. Podle toho **základní** podskupinu v **správce odkazů** nebude výčet žádné sestavení ze systému Windows 8 SDK a místo toho zobrazí zpráva: "sady Windows SDK je již odkazovat. Použijte prohlížeč objektů a prozkoumejte odkazy v sadě Windows SDK."

V běžných projektů **základní** podskupinu se nezobrazí ve výchozím nastavení. Prostředí Windows Runtime můžete přidat tak, že otevřete místní nabídce uzlu projektu výběr **uvolnit projekt**, přidání následující fragment kódu a opakovaným otevřením projektu (na uzel projektu zvolte **znovu načíst projekt**). Při vyvolání **správce odkazů** dialogové okno, **základní** podskupinu se zobrazí.

```xml
<PropertyGroup>
  <TargetPlatformVersion>8.0</TargetPlatformVersion>
</PropertyGroup>
```

Je nutné vybrat **Windows** v tato podskupina zaškrtávací políčko. Poté budete moci používat elementy prostředí Windows Runtime. Však budete také chtít přidat <xref:System.Runtime>, v prostředí Windows Runtime určující některé standardní třídy a rozhraní, například <xref:System.Collections.IEnumerable>, které se používají v rámci prostředí Windows Runtime knihoven. Informace o tom, jak přidat <xref:System.Runtime>, najdete v části [spravované aplikace klasické pracovní plochy a prostředí Windows Runtime](http://msdn.microsoft.com/library/windows/apps/jj856306.aspx#consuming_standard_windows_runtime_types).

### <a name="extensions-subgroup"></a>Rozšíření podskupinu

**Rozšíření** uvádí uživatele sady SDK, které rozšiřují cílové platformy Windows. Na této kartě se zobrazí Windows 8.x Store aplikaci pouze pro projekty. Běžných projektů nebudou na této kartě Zobrazit, protože mohou spotřebovat pouze první strany *.winmd* soubory.

Sada SDK je kolekce souborů, které sada Visual Studio považuje za jedinou součást. V **rozšíření** kartě, sady SDK, které platí pro projekt, ze kterých **správce odkazů** byl vyvolán dialogové okno jsou uvedeny jako položky jednou. Při přidání do projektu, veškerý obsah sady SDK je spotřebovávají Visual Studio tak, aby uživatel nemusí provádět žádné další akce využívat obsah sady SDK technologie IntelliSense, sada nástrojů, návrháře, prohlížeč objektů, sestavení, nasazení, ladění a zabalení. Informace o tom, jak zobrazit vaše SDK v **rozšíření** kartě najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md).

> [!NOTE]
> Pokud projekt odkazuje na sadu SDK, které závisí na jiné sady SDK, Visual Studio nebude využívat druhý SDK, pokud uživatel ručně přidá odkaz na druhý SDK. Když uživatel vybere sadu SDK na **rozšíření** kartě **správce odkazů** uživateli identifikovat SDK závislosti tak, že uvedete nejen název a verzi sady SDK, ale také název žádné SDK pomáhá dialogové okno závislosti v podokně podrobností. Pokud je uživatel nebude Všimněte si, závislosti a přidá jenom SDK, MSBuild vyzve uživatele, přidání závislosti.

Pokud typ projektu nepodporuje rozšíření, na kartě nezobrazí v **správce odkazů** dialogové okno.

## <a name="com-tab"></a>Karta COM

**COM** karta obsahuje všechny komponenty COM, které jsou k dispozici pro odkazování. Pokud chcete přidat odkaz na registrovanou knihovnu DLL modelu COM, která obsahuje vnitřní manifest, nejprve zrušte registraci dané knihovny DLL. Visual Studio, jinak hodnota přidá odkaz na sestavení jako ovládací prvek ActiveX místo jako nativní knihovny DLL.

Pokud typ projektu nepodporuje COM, na kartě nezobrazí v **správce odkazů** dialogové okno.

## <a name="browse-button"></a>Tlačítko Procházet

Můžete použít **Procházet** tlačítko procházení pro součást v systému souborů.

Projekt se může odkazovat na součást, která cílí na jinou verzi rozhraní .NET Framework. Například můžete vytvořit aplikace s cílem 4.7 rozhraní .NET Framework, který odkazuje na komponentu, která je cílena na rozhraní .NET Framework 4. Další informace najdete v tématu [přehled cílení na více](../ide/visual-studio-multi-targeting-overview.md).

Měli byste se vyhnout přidávání odkazů na soubory do výstupů jiného projektu ve stejném řešení, protože to může vést k chybám při kompilaci. Místo toho použijte **řešení** kartě **správce odkazů** dialogové okno vytvořit odkazy na projekt na projekt. To usnadňuje vývoj v týmu tím, že umožňuje lepší správu knihovny tříd, které vytvoříte v projektech. Další informace najdete v tématu [Poradce při potížích přerušený odkazy](../ide/troubleshooting-broken-references.md).

Nelze procházet sadě SDK a přidejte do projektu. Pouze můžete vyhledat soubor (například sestavení nebo *.winmd*) a přidejte ji do projektu.

Při provádění odkaz na sestavení souboru WinMD, očekávané rozložení je, že  *<FileName>.winmd*,  *<FileName>.dll*, a  *<FileName>.pri* jsou soubory všechny umístěny vedle sebe navzájem. Pokud odkazujete na soubor WinMD v následujících scénářích, do výstupního adresáře projektu budou zkopírovány neúplné sady souborů a v důsledku toho dojde k chybám při sestavení a za běhu.

- **Nativní součást**: k nativnímu projektu vytvoří jeden WinMD pro každý nesouvislé Sada oborů názvů a jednu knihovnu DLL, která se skládá z implementace. Soubory WinMDs budou mít nesouvislé názvy. Při odkazování na tento soubor nativní součásti, nástroje MSBuild nerozpozná, dissimilarly pojmenované WinMDs vytvořili jednu součást. V důsledku toho pouze stejně jako s názvem  *<FileName>.dll* a  *<FileName>.winmd* se zkopírují, a dojde k chybám za běhu. Chcete-li tento problém obejít, vytvořte rozšíření sady SDK. Další informace najdete v tématu [vytvořit Software Development Kit](../extensibility/creating-a-software-development-kit.md).

- **Použití ovládacích prvků**: minimálně ovládacího prvku XAML se skládá z  *<FileName>.winmd*,  *<FileName>.dll*,  *<FileName>.pri*,  *<XamlName>XAML*a  *<ImageName>.jpg*. Při sestavení projektu, soubory prostředků, které jsou spojeny s odkazem na soubor nezískáte zkopírovaný do výstupního adresáře projektu a to pouze  *<FileName>.winmd*,  *<FileName>.dll*a  *<FileName>.pri* budou zkopírovány. Chyby sestavení přihlášen uživatel informován o který prostředky  *<XamlName>XAML* a  *<ImageName>.jpg* chybí. Aby sestavení proběhlo úspěšně, bude uživatel muset ručně zkopírovat tyto soubory prostředků do výstupního adresáře projektu pro sestavení a ladění/dobu běhu. Chcete-li tento problém obejít, buď vytvořit sady extension SDK podle kroků v [vytvořit Software Development Kit](../extensibility/creating-a-software-development-kit.md) nebo upravit projektu souboru přidejte následující vlastnost:

    ```xml
    <PropertyGroup>
       <GenerateLibraryOutput>True</GenerateLibraryOutput>
    </PropertyGroup>
    ```

    > [!NOTE]
    > Pokud tuto vlastnost přidáte, může být sestavení pomalejší.

## <a name="recent"></a>Nedávné

**Sestavení**, **COM**, **Windows**, a **Procházet** každý podporu **poslední** kartu, která zobrazí seznam komponenty, které byly nedávno přidané do projektů.

## <a name="search"></a>Hledat

V řádku hledání **správce odkazů** dialogové okno funguje přes kartu, která je aktivní. Například, pokud uživatel zadá "Systém" v panelu vyhledávání při **řešení** karta je aktivní, hledání nevrátí žádné výsledky, pokud řešení se skládá z název projektu, který obsahuje "Systém".

## <a name="see-also"></a>Viz také

- [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)