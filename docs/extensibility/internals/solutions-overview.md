---
title: Přehled řešení
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- solutions, about solutions
ms.assetid: 3b21e3a1-170a-4485-941e-6b04b7b27886
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9405177e193349eeb6e7767b70af0ef82208cc4c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322596"
---
# <a name="solutions-overview"></a>Přehled řešení

Řešení je seskupení jednoho nebo více projektů, které vzájemně spolupracují na vytvoření aplikace. Projekt a stavové informace týkající se řešení jsou uloženy ve dvou souborech jiné řešení. [Soubor řešení (.sln)](solution-dot-sln-file.md) je založený na textu a můžete umístit pod správou zdrojového kódu a sdílet mezi uživateli. [Řešení uživatelské možnosti (.suo) soubor](solution-user-options-dot-suo-file.md) binární. Soubor .suo v důsledku toho nemůže být umístěn pod správou zdrojového kódu a obsahuje informace specifické pro uživatele.

Žádné VSPackage lze zapisovat do obou typů souborů řešení. Vzhledem k povaze soubory existují dvě různá rozhraní implementována pro zápis do nich. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> Rozhraní textové informace zapisuje do souboru .sln a <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> rozhraní zapíše do souboru .suo binární datové proudy.

> [!NOTE]
> Projekt není nutné explicitně zápis záznamu pro samotné do souboru řešení. prostředí, která zpracovává pro projekt. Proto pokud chcete přidat další obsah konkrétně do souboru řešení, není potřeba registrovat vašeho balíčku VSPackage tímto způsobem.

Každý VSPackage podpora trvalosti řešení používá tři rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> rozhraní, které je implementované prostředí a volané sady VSPackage, a `IVsPersistSolutionProps` a `IVsPersistSolutionOpts`, které jsou obě implementované sady VSPackage. `IVsPersistSolutionOpts` Rozhraní pouze musí implementovat, pokud má být sady VSPackage zapsaného do souboru .suo soukromé informace.

Po otevření řešení následující proces probíhá.

1. Prostředí přečte řešení.

2. Pokud najde prostředí `CLSID`, načte odpovídající VSPackage.

3. Pokud je VSPackage načteny, volání prostředí `QueryInterface` pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> rozhraní pro rozhraní, které vyžaduje sady VSPackage.

   - Při čtení ze souboru .sln, prostředí volá `QueryInterface` pro `IVsPersistSolutionProps`.

   - Při čtení ze souboru .suo, prostředí volá `QueryInterface` pro `IVsPersistSolutionOpts`.

   Konkrétní informace týkající se použití těchto souborů můžete najít v [řešení (. SLN) soubor](../../extensibility/internals/solution-dot-sln-file.md) a [uživatelské možnosti řešení (. Soubor suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md).

> [!NOTE]
> Pokud chcete vytvořit novou konfiguraci řešení skládající se z konfigurace dva projekty a vyloučení třetí ze sestavení, budete muset použít uživatelské rozhraní vlastností stránky nebo služby automation. Správce konfigurace sestavení řešení a jejich vlastnosti nelze změnit přímo, ale můžete pracovat s použitím správci sestavení řešení `SolutionBuild` třídy z DTE v modelu automatizace. Další informace o konfiguraci řešení najdete v tématu [konfigurace řešení](../../extensibility/internals/solution-configuration.md).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>