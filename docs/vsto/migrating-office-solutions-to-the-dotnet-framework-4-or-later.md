---
title: "Migrace řešení Office na rozhraní .NET Framework 4 nebo novější | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords: Office projects [Office development in Visual Studio], migrating to .NET Framework 4
ms.assetid: 31f6c48b-c086-4362-8629-f644d6083a44
caps.latest.revision: "55"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c47c99f8d9a907d86461098f1f569fdbcac8841c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="migrating-office-solutions-to-the-net-framework-4-or-later"></a>Migrace řešení Office na rozhraní .NET Framework 4 nebo novější
  Pokud cílový framework projektu Office se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později ze starší verze rozhraní .NET Framework, některé další kroky k bude pravděpodobně nutné nadále spouštět řešení na vývoj a koncový uživatel počítače. Další informace najdete v tématu [požadované změny pro spouštění projektů Office, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).  
  
 Kromě toho může nadále kompilovány projektu. Některé funkce projektů Office mají různé programovací modely pro různé verze rozhraní .NET Framework. Když se změní cílový framework projektu Office na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo ze starší verze rozhraní .NET Framework, musíte později provést následující změny kódu, do projektu:  
  
-   [Aktualizace projektů Excel a Word při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
 Cílový framework projektu Office se změní při upgradu tohoto projektu ze starší verze sady Visual Studio. Další informace najdete v tématu [upgrade a migrace řešení Office](../vsto/upgrading-and-migrating-office-solutions.md).  
  
 Další informace o tom, proč některé funkce v projektech Office mají různé programovací model, pokud cílíte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, najdete na [změny návrhu systému Office projekty, cílí na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md) a [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="see-also"></a>Viz také  
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [Řešení potíží s chybami v řešeních pro systém Office](../vsto/troubleshooting-errors-in-office-solutions.md)   
 [Další podpora pro chyby v řešeních pro systém Office](../vsto/additional-support-for-errors-in-office-solutions.md)  
  
  