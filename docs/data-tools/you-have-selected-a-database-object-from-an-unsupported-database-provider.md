---
title: Vybrali jste databázový objekt od nepodporovaného poskytovatele databáze.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 209ab92e3a24733e2ef4b7b912a36ae920ffffdb
ms.sourcegitcommit: 59c48e1e42b48ad25a4e198af670faa4d8dae370
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54204242"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>Vybrali jste databázový objekt od nepodporovaného poskytovatele databáze.

**O/R Designer** podporuje pouze zprostředkovatele dat .NET Framework pro SQL Server (<xref:System.Data.SqlClient>). I když můžete kliknout na **OK** a pokračovat v práci s objekty od poskytovatelů Nepodporovaná databáze, vám může dojít k neočekávanému chování za běhu.

> [!NOTE]
> Jsou podporovány pouze datová připojení, které používají zprostředkovatele dat .NET Framework pro SQL Server.

## <a name="options"></a>Možnosti

- Klikněte na tlačítko **OK** pokračujte návrhu tříd entit, které mapují na připojení, které používá nepodporovaného poskytovatele databáze. Při použití nepodporované databázové poskytovatelů, může dojít k neočekávanému chování.

- Klikněte na tlačítko **zrušit** zastavit akci. Vytvořit nebo použít odlišné datové připojení, který používá zprostředkovatele .NET Framework pro SQL Server.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)