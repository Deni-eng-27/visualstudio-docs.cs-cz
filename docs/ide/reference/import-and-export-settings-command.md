---
title: nastavení importu a exportu – příkaz
ms.date: 11/21/2018
ms.topic: reference
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9be5826edf0d7220d30ce5c4a99f333c2ab8b67
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55947221"
---
# <a name="import-and-export-settings-command"></a>nastavení importu a exportu – příkaz

Importuje, exportuje nebo obnoví nastavení sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```cmd
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]
```

## <a name="switches"></a>Přepínače

/export:`filename`

Volitelné. Exportuje aktuální nastavení do zadaného souboru.

/import:`filename`

Volitelné. Naimportuje ho do zadaného souboru.

/ Reset

Volitelné. Obnoví aktuální nastavení.

## <a name="remarks"></a>Poznámky

Spuštění tohoto příkazu bez přepínače otevře **nastavení importu a exportu** průvodce. Další informace najdete v tématu [synchronizovat nastavení](../synchronized-settings-in-visual-studio.md) a [nastavení prostředí](../environment-settings.md).

## <a name="example"></a>Příklad

Následující příkaz exportuje aktuální nastavení do souboru `MyFile.vssettings`:

```cmd
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>Viz také:

- [Nastavení prostředí](../../ide/environment-settings.md)
- [Synchronizovat nastavení](../../ide/synchronized-settings-in-visual-studio.md)
- [Přizpůsobení prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)