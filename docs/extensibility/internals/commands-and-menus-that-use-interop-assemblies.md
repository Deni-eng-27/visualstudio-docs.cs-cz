---
title: Příkazy a nabídky používající definiční sestavení | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, using interop assemblies
- interop assemblies, using in commands and menus
- commands, handling using interop assemblies
- command handling with interop assemblies
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e6c381abe9b4c6ea2a58342e185d7427fa56a180
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709487"
---
# <a name="commands-and-menus-that-use-interop-assemblies"></a>Příkazy a nabídky používající definiční sestavení
VSPackage, který implementuje příkazy nabídky a panelu nástrojů pomocí sestavení interop, musí:

- Informujte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) o podporovaných příkazech a o tom, jestli jsou momentálně povolené.

- Dodržovat pravidla (kontrakt) pro zpracování příkazů.

- Explicitně implementujte zpracování příkazů pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní nebo.

  Následující část popisuje, jak provádět tyto úlohy.

## <a name="in-this-section"></a>V této části
- [Určení stavu příkazu pomocí definičních sestavení](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)

 Popisuje, jakým způsobem VSPackage oznamuje rozhraní IDE, které příkazy podporuje a zda jsou aktuálně povoleny.

- [Kontrakty příkazů v sestaveních spolupráce](../../extensibility/internals/command-contracts-in-interop-assemblies.md)

 Poskytuje definici základní kontraktu příkazu, který používají všechny sady VSPackage implementující příkazy pomocí sestavení Interop.

- [Implementace příkazu](../../extensibility/internals/command-implementation.md)

 Poskytuje přehled o tom, jak VSPackage implementuje příkaz.

- [Obslužné rutiny příkazu registrovat definiční sestavení](../../extensibility/internals/registering-interop-assembly-command-handlers.md)

 Popisuje položky registru potřebné pro oznamování integrovanému vývojovému prostředí (IDE), které rozhraní VSPackage poskytuje obslužnou rutinu příkazu.

## <a name="related-sections"></a>Související oddíly
- [Dostupnost příkazu](../../extensibility/internals/command-availability.md)

 Popisuje kritéria, která jsou používána rozhraním IDE k určení, které příkazy VSPackage jsou k dispozici a které objekt je zpracovává.

- [Jak prvky VSPackage přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)

 Obsahuje podrobné informace o tom, jak vytvořit uživatelské rozhraní, které používá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporu příkazů.

- [Směrování příkazů v VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)

 Přehled procesu sloužícího k přidružení objektu ke správné žádosti o příkaz.
