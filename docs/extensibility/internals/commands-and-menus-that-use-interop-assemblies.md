---
title: Příkazy a nabídky, které používají spolupracující sestavení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, using interop assemblies
- interop assemblies, using in commands and menus
- commands, handling using interop assemblies
- command handling with interop assemblies
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d08e7ad95e621ab444f98c295f5d84aa2b6e0066
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62910706"
---
# <a name="commands-and-menus-that-use-interop-assemblies"></a>Příkazy a nabídky, které používají spolupracující sestavení
Musí se VSPackage, která implementuje příkazy nabídek a panelů nástrojů pomocí spolupracujícího sestavení:

- Informujte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) o příkazech podporuje a určuje, zda jsou aktuálně povoleny.

- Proto zavázala dodržovat pravidla (smlouvy) pro zpracování příkazů.

- Explicitní implementace manipulaci s použitím buď <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní.

  Následující část popisuje, jak k provádění těchto úkolů.

## <a name="in-this-section"></a>V tomto oddílu
- [Určení stavu příkazu pomocí spolupracujícího sestavení](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)

 Popisuje, jak VSPackage upozorní rozhraní IDE o příkazech, které podporuje, a určuje, zda jsou aktuálně povoleny.

- [Kontrakty příkazů ve spolupracujícím sestavení](../../extensibility/internals/command-contracts-in-interop-assemblies.md)

 Poskytuje definici kontraktu základní příkaz používá všechna rozšíření VSPackages provádění příkazů pomocí sestavení vzájemné spolupráce.

- [Implementace příkazu](../../extensibility/internals/command-implementation.md)

 Poskytuje přehled o způsob VSPackage implementace příkazu.

- [Zaregistrujte obslužné rutiny příkazů spolupracujícího sestavení](../../extensibility/internals/registering-interop-assembly-command-handlers.md)

 Popisuje položky registru, který je potřeba upozornit integrované vývojové prostředí, že poskytuje VSPackage obslužná rutina příkazu.

## <a name="related-sections"></a>Související oddíly
- [Dostupnost příkazu](../../extensibility/internals/command-availability.md)

 Popisuje kritéria, která se používají integrovaným vývojovým prostředím určíte, které VSPackage příkazy jsou k dispozici a objekt je zpracovává.

- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)

 Obsahuje podrobné informace o tom, jak vytvořit uživatelské rozhraní, která používá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkaz podpory.

- [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)

 Přehled procesu je používán k propojení objektu s žádostí o správný příkaz.