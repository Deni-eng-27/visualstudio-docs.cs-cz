---
title: Nástroj CreatePkgDef | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9f437eb3586dc16bb0b4b9eb60cd303eb90db6c3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709158"
---
# <a name="createpkgdef-utility"></a>Nástroj CreatePkgDef
Převezme soubor DLL pro rozšíření sady Visual Studio jako parametr a vytvoří soubor *. pkgdef* , který se doprovází k souboru *. dll* . Soubor *. pkgdef* obsahuje všechny informace, které by jinak byly zapsány do systémového registru při instalaci rozšíření.

> [!NOTE]
> Většina šablon projektů, které jsou součástí sady Visual Studio SDK, automaticky vytvoří soubory *. pkgdef* jako součást procesu sestavení. Tento dokument je určený pro uživatele, kteří chtějí balíčky vytvořit ručně, nebo převeďte stávající balíčky na použití nasazení *. pkgdef*  .

## <a name="syntax"></a>Syntaxe

```
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>
```

## <a name="arguments"></a>Argumenty
**/out = &lt; filename&gt;**\
Povinná hodnota. Nastaví název výstupního souboru *. pkgdef* na &lt; název souboru &gt; .

**/codebase**\
Nepovinný parametr. Vynutí registraci pomocí nástroje **codebase** .

**/Assembly je**\
Vynutí registraci pomocí nástroje **Assembly** .

**&lt;AssemblyPath&gt;**\
Cesta k souboru *. dll* , ze kterého chcete generovat soubor *. pkgdef*.

## <a name="remarks"></a>Poznámky
Nasazení rozšíření pomocí souborů *. pkgdef* nahrazuje požadavky v registru dřívějších verzí sady Visual Studio.

::: moniker range=">=vs-2019"

Soubory *. pkgdef* musí být nainstalované v jednom z následujících umístění:

- *%localappdata%\Microsoft\Visual Studio\16.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

Pokud je instalační složka *%localappdata%\Microsoft\Visual Studio\16.0\Extensions \\ *, je rozšíření rozpoznáno v aplikaci Visual Studio, ale je ve výchozím nastavení zakázáno. Uživatel může rozšíření povolit pomocí **možnosti spravovat rozšíření**.

Pokud je instalační složka *%VSINSTALLDIR%\Common7\IDE\Extensions \\ *, je ve výchozím nastavení povolená přípona.

> [!NOTE]
> Nástroj **Spravovat rozšíření** nelze použít pro přístup k rozšíření, pokud není nainstalován jako součást balíčku VSIX.

::: moniker-end

::: moniker range="vs-2017"

Soubory *. pkgdef* musí být nainstalované v jednom z následujících umístění:

- *%localappdata%\Microsoft\Visual Studio\15.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

Pokud je instalační složka *%localappdata%\Microsoft\Visual Studio\15.0\Extensions \\ *, je rozšíření rozpoznáno v aplikaci Visual Studio, ale je ve výchozím nastavení zakázáno. Uživatel může rozšíření povolit pomocí **rozšíření a aktualizací**.

Pokud je instalační složka *%VSINSTALLDIR%\Common7\IDE\Extensions \\ *, je ve výchozím nastavení povolená přípona.

> [!NOTE]
> Nástroj **rozšíření a aktualizace** nelze použít pro přístup k rozšíření, pokud není nainstalován jako součást balíčku VSIX.

::: moniker-end

## <a name="see-also"></a>Viz také
- [Nástroj CreateExpInstance](../../extensibility/internals/createexpinstance-utility.md)
