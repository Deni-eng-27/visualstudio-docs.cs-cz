---
title: Registrace operací pro přípony názvů souborů | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- verbs, registering
ms.assetid: 81a58e40-7cd0-4ef4-a475-c4e1e84d6e06
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ac2854f1799075cc14d9beb557335be5228be21d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80701536"
---
# <a name="register-verbs-for-file-name-extensions"></a>Registrovat operace pro přípony názvů souborů
Přidružení přípony názvu souboru k aplikaci má obecně upřednostňovanou akci, která nastane, když uživatel dvakrát klikne na soubor. Tato upřednostňovaná akce je propojena s operací, například otevřít, která odpovídá akci.

 Můžete registrovat příkazy, které jsou přidruženy k programovému identifikátoru (ProgID) pro rozšíření pomocí klíče prostředí, který se nachází v **HKEY_CLASSES_ROOT \{ ProgID} \Shell**. Další informace najdete v tématu [typy souborů](/windows/desktop/shell/fa-file-types).

## <a name="register-standard-verbs"></a>Registrovat standardní příkazy
 Operační systém rozpoznává následující standardní příkazy:

- Otevřená

- Upravit

- Zobrazovaný

- Tiskový

- Preview

  Kdykoli je to možné, zaregistrujte standardní příkaz. Nejběžnější volbou je otevřená operace. Příkaz Edit použijte pouze v případě, že existuje jasný rozdíl mezi otevřením souboru a úpravou souboru. Například otevření souboru *. htm* se zobrazí v prohlížeči, zatímco úprava souboru *. htm* spustí editor HTML. Standardní příkazy jsou lokalizovány do národního prostředí operačního systému.

> [!NOTE]
> Při registraci standardního slovesa Nenastavujte výchozí hodnotu pro otevřený klíč. Výchozí hodnota obsahuje řetězec zobrazení v nabídce. Operační systém dodává tento řetězec pro standardní slovesa.

 Soubory projektu by měly být registrovány pro spuštění nové instance, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] když uživatel otevře soubor. Následující příklad znázorňuje standardní registraci příkazu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekt.

```
[HKEY_CLASSES_ROOT\.csproj]
@="VisualStudio.csproj.8.0"

[HKEY_CLASSES_ROOT\.csproj\OpenWithList]
[HKEY_CLASSES_ROOT\.csproj\OpenWithList\VSLauncher.exe]
@=""

[HKEY_CLASSES_ROOT\.csproj\OpenWithProgids]
"VisualStudio.csproj.8.0"=""

[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe]
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell]
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open]
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open\Command]
@="C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe \"%1\""

[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0]
@="C# Project file"

[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\DefaultIcon]
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,0"

[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell]
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open]
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open\Command]
@="\"C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe\" \"%1\""
```

 Pokud chcete otevřít soubor v existující instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , zaregistrujte klíč DDEEXEC. Následující příklad znázorňuje standardní registraci operací pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] soubor *. cs* .

```
[HKEY_CLASSES_ROOT\.cs]
@="VisualStudio.cs.8.0"

[HKEY_CLASSES_ROOT\.cs\OpenWithList]
[HKEY_CLASSES_ROOT\.cs\OpenWithList\devenv.exe]
@=""

[HKEY_CLASSES_ROOT\.cs\OpenWithProgids]
"VisualStudio.cs.8.0"=""

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0]
@="C# Source file"

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\DefaultIcon]
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,1"

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell]
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open]
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\Command]
@="\"C:\\VisualStudioPath\\Common7\\IDE\\devenv.exe\" /dde \"%1\""

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec]
@="Open(\"%1\")"

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Application]
@="VisualStudio.8.0"

[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Topic]
@="system"
```

## <a name="set-the-default-verb"></a>Nastavit výchozí příkaz
 Výchozí operace je akce, která se spustí, když uživatel dvakrát klikne na soubor v Průzkumníkovi Windows. Výchozí příkaz je operace zadaná jako výchozí hodnota pro **HKEY_CLASSES_ROOT klíč \\ \Shell*ProgID*** . Pokud není zadána žádná hodnota, výchozím příkazem je první příkaz určený v seznamu **HKEY_CLASSES_ROOTho \Shell \\ *ProgID*** Key.

> [!NOTE]
> Pokud máte v úmyslu změnit výchozí operaci pro rozšíření při souběžném nasazení, zvažte dopad na instalaci a odebrání. Během instalace je původní výchozí hodnota přepsána.

## <a name="see-also"></a>Viz také
- [Spravovat přidružení souborů vedle sebe](../extensibility/managing-side-by-side-file-associations.md)
