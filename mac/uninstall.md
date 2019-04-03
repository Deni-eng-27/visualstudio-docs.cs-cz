---
title: Uninstall Visual Studio for Mac
description: Pokyny k odinstalaci sady Visual Studio pro Mac a související nástroje.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: ef208a9f74c1c8ee1ccb6df2c1e54917cd354be3
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856444"
---
# <a name="uninstalling-visual-studio-for-mac"></a>Odinstalace sady Visual Studio pro Mac

Existuje několik produktů Xamarin, které umožňují vývoj aplikací napříč platformami, včetně samostatné aplikace, jako je Visual Studio pro Mac.

Tato příručka slouží k odinstalaci jednotlivých produktů jednotlivě tak, že přejdete do příslušné části, nebo můžete použít skripty v [skript](#uninstall-script) část týkající se odinstalace všechno.

Pokud jste dřív měli Xamarin Studio v počítači byly nainstalovány, budete také muset postupujte podle pokynů v [společnosti Xamarin odinstalovat](/xamarin/cross-platform/get-started/installation/uninstalling-xamarin#uninstall-xamarin-studio-on-mac) průvodce, kromě následujících kroků.

## <a name="uninstall-script"></a>Odinstalace skriptu

Existují dva skripty, které lze použít k odinstalaci sady Visual Studio pro Mac a všechny komponenty pro váš počítač:

- [Skript sady Visual Studio a Xamarin](#visual-studio-for-mac-and-xamarin-script)
- [Skript .NET core](#net-core-script)

Následující části poskytují informace o stahování a pomocí skriptů.

### <a name="visual-studio-for-mac-and-xamarin-script"></a>Visual Studio pro Mac a Xamarin skriptu

Odinstalujete Visual Studio a Xamarin komponenty v jednom přejít pomocí [odinstalovat skript](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh).

Tento skript pro odinstalaci obsahuje většinu příkazů, které najdete v článku. Existují tři hlavní opomenutí ze skriptu a nejsou zahrnuty z důvodu možných externích závislostí. K odstranění této, přejít do příslušné části níže a je odebrat ručně:

- **[Odinstalace Mono](#uninstall-mono-sdk-mdk)**
- **[Probíhá odinstalace AVD na Androidu](#uninstall-android-avd)**
- **[Odinstalace Android SDK a Java SDK](#uninstall-android-sdk-and-java-sdk)**

Spusťte skript, proveďte následující kroky:

1. Klikněte pravým tlačítkem na skript a vyberte **uložit jako** k uložení souboru na vašem počítači Mac.
2. Otevřete terminál a přejděte ve kterém se skript stáhl pracovní adresář:

    ```bash
    cd /location/of/file
    ```
3. Spustitelný soubor skriptu a spustit ji s **sudo**:

    ```bash
    chmod +x ./uninstall-vsmac.sh
    sudo ./uninstall-vsmac.sh
    ```
4. Nakonec odstraňte skript pro odinstalaci.

### <a name="net-core-script"></a>Skript .NET core

Skript pro odinstalaci pro .NET Core se nachází v [úložiště rozhraní příkazového řádku dotnet](https://raw.githubusercontent.com/dotnet/cli/master/scripts/obtain/uninstall/dotnet-uninstall-pkgs.sh)

Spusťte skript, proveďte následující kroky:

1. Klikněte pravým tlačítkem na skript a vyberte **uložit jako** k uložení souboru na vašem počítači Mac.
2. Otevřete terminál a přejděte ve kterém se skript stáhl pracovní adresář:

    ```bash
    cd /location/of/file
    ```
3. Spustitelný soubor skriptu a spustit ji s **sudo**:

    ```bash
    chmod +x ./dotnet-uninstall-pkgs.sh
    sudo ./dotnet-uninstall-pkgs.sh
    ```
4. Nakonec odstraňte skript pro odinstalaci .NET Core.

## <a name="uninstall-visual-studio-for-mac"></a>Uninstall Visual Studio for Mac

Prvním krokem při odinstalaci sady Visual Studio na macu, je nalezení **Visual Studio.app** v **/Applications** adresáře a přetáhněte ji do **koše**. Alternativně klepněte pravým tlačítkem myši a vyberte **přesunout do koše** jak je znázorněno na následujícím obrázku:

![Aplikace Visual Studio přesunout do koše](media/uninstall-image1.png)

Odstraněním této sady prostředků aplikace dojde k odebrání sady Visual Studio pro Mac, i když může být souborů souvisejících s Xamarin stále v systému souborů.

Chcete-li odebrat všechna trasování sady Visual Studio pro Mac, spuštěním následujících příkazů v terminálu:

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf ~/Library/Preferences/Visual\ Studio
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Application\ Support/VisualStudio
rm -rf ~/Library/Application\ Support/VisualStudio/7.0/LocalInstall/Addins/
rm -rf ~/Library/Application\ Support/VisualStudio/8.0/LocalInstall/Addins/
```

Můžete také odebrat následující adresáře, který obsahuje různé Xamarin soubory a složky. Nicméně než se pustíte do byste měli vědět, že tento adresář obsahuje Android podpisových klíčů. Další informace najdete v části  **[odinstalaci sady Android SDK a sady Java SDK](#uninstall-android-sdk-and-java-sdk)**:

```bash
rm -rf ~/Library/Developer/Xamarin
```


## <a name="uninstall-mono-sdk-mdk"></a>Odinstalujte modul Mono SDK (MDK)

Mono je open source implementace rozhraní .NET Framework společnosti Microsoft a umožňují tak, že všechny Xamarin Products—Xamarin.iOS, Xamarin.Android a Xamarin.Mac vývoj z těchto platforem v jazyce C#.

> [!WARNING]
> Existují další aplikace mimo sadu Visual Studio pro Mac využívající Mono, jako je Unity.
> Ujistěte se, že neexistují žádné závislosti na Mono před odinstalací.

Pokud chcete z počítače odebrat Mono Frameworku, spuštěním následujících příkazů v terminálu:

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Uninstall Xamarin.Android

Existuje několik položek, které jsou potřebné pro instalaci a použití Xamarin.Android, jako jsou sady Android SDK a sady Java SDK.

Chcete-li odebrat Xamarin.Android, použijte následující příkazy:

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Odinstalace Android SDK a Java SDK

Sady Android SDK je vyžadována pro vývoj aplikací pro Android. K úplnému odebrání všech součástí sady Android SDK, vyhledávat soubor za **~/Library/Developer/Xamarin/** a přesuňte ho do **koše**.

> [!WARNING]
> Je třeba si uvědomit, že Android podpisové klíče, které jsou vygenerovány sadou Visual Studio for Mac jsou umístěny v `~/Library/Developer/Xamarin/Keystore`. Ujistěte se, že tyto správně zálohovat nebo -li zabránit odebrání tohoto adresáře, pokud chcete zachovat úložiště klíčů.

Java SDK (JDK) není nutné odinstalovat, protože je již předběžně zabalen jako součást systému Mac OS X / macOS.

### <a name="uninstall-android-avd"></a>Odinstalace Android AVD

> [!WARNING]
> Existují jiné aplikace mimo sadu Visual Studio pro Mac, které také používají Android AVD a tyto další součásti pro android, jako je například Android Studio.Removing tento adresář může způsobit, že projekty přerušení v nástroji Android Studio.

Chcete-li odebrat všechny Avd Android a další Android součásti použijte následující příkaz:

```bash
rm -rf ~/.android
```

Chcete-li odebrat jenom Android Avd použijte následující příkaz:

```bash
rm -rf ~/.android/avd
```

## <a name="uninstall-xamarinios"></a>Uninstall Xamarin.iOS

Xamarin.iOS umožňuje vývoj pro iOS aplikace s využitím C# nebo F# pomocí sady Visual Studio pro Mac.

Pomocí následujících příkazů v terminálu odeberte všechny soubory Xamarin.iOS systému souborů:

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Odinstalujte Xamarin.Mac

Xamarin.Mac lze odebrat z počítače tento kyberzločinec odstranit produkt a licenci z počítače Mac pomocí následujících příkazů:

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Odinstalujte sešity a inspektoru

Počínaje 1.2.2, sešity ke Xamarinu & Kontrola můžou se odinstalovat z terminálu spuštěním:

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

Pro starší verze budete muset ručně odebrat následující artefakty:

* Odstranit sešity aplikace na adrese `"/Applications/Xamarin Workbooks.app"`
* Odstranit inspektoru aplikace na adrese `"Applications/Xamarin Inspector.app"`
* Odstranit doplňků: `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` a `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"`
* Odstranit Inspector a podpůrné soubory. tady: `/Library/Frameworks/Xamarin.Interactive.framework` a `/Library/Frameworks/Xamarin.Inspector.framework`

## <a name="uninstall-the-xamarin-profiler"></a>Odinstalujte Xamarin Profiler

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Odinstalace instalačního programu sady Visual Studio

Chcete-li odebrat všechna trasování Xamarin univerzální instalačního programu použijte následující příkazy:

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```

## <a name="uninstall-visual-studio-2019-for-mac-preview"></a>Odinstalace Visual Studio 2019 for Mac Preview

2019 Visual Studio for Mac Preview byl spuštěn jako samostatné verze preview, abyste mohli pokračovat v práci s Visual Studio 2017 for Mac nainstalovat vedle sebe.

Teď, když vydala 2019 Visual Studio pro Mac teď můžete bezpečně odebrat Visual Studio 2019 aplikace Mac ve verzi Preview.

Odinstalace sady prostředků aplikace ve verzi preview, vyberte **sady Visual Studio (Preview)** z vaší **aplikací** složky a klikněte na tlačítko **přesunout do koše**, jak je znázorněno v následujícím Obrázek:

![Výběrem možnosti "přesunout do koše" ve Finderu.](media/uninstall-remove-vspreview.png)

Můžete také odebrat náhled souboru plist pomocí následujícího příkazu:

```bash
rm -rf ~/Library/Preferences/com.microsoft.visual-studio-preview.plist
```

## <a name="see-also"></a>Viz také:

- [Odinstalace sady Visual Studio (ve Windows)](/visualstudio/install/uninstall-visual-studio)