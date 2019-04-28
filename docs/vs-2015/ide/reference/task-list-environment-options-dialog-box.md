---
title: Seznam úkolů, prostředí, dialogové okno Možnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.Task_List
- VS.ToolsOptionsPag.Environment.Task_List
- VS.ToolsOptionsPages.Environment.TaskList
- VS.Environment.Task List
helpviewer_keywords:
- Token List
- tokens
- icons, in Task List
- Task List, customizing environment
- Options dialog box, Task List environment
- exclamation points
- comments, comment tasks in Task List
- tokens, and the Task List
- Task List, comment tasks
ms.assetid: 88327e04-fa3e-48db-995b-ad89e0dc4ed2
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0d24556be75547a4944ad1faca47c4545f8812ba
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410031"
---
# <a name="task-list-environment-options-dialog-box"></a>Seznam úkolů, prostředí, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tato stránka možností umožňuje přidat, odstranit a změnit tokeny komentáře, které generují **seznamu úkolů** připomenutí. Chcete-li zobrazit tato nastavení, vyberte **možnosti** z **nástroje** nabídky, rozbalte **prostředí** složky a zvolte **seznamu úkolů**.  
  
## <a name="task-list-options"></a>Nastavení seznamu úkolů  
 Potvrdit odstranění úlohy  
 Pokud je vybráno, pokaždé, když se odstranění uživatelského úkolu ze, zobrazí se okno se zprávou **seznamu úkolů**, umožňuje potvrďte odstranění. Ve výchozím nastavení je vybraná tato možnost.  
  
> [!NOTE]
> Odstranit komentář k úkolu, použijte odkaz k nalezení komentář a pak ji odebrat z vašeho kódu.  
  
 Zobrazovat pouze názvy souborů  
 Při výběru, **souboru** sloupec **seznamu úkolů** zobrazuje pouze názvy souborů, které mají být upravena, není jejich úplné cesty.  
  
## <a name="tokens"></a>Tokeny  
 Když vložíte komentář do svého kódu, jejichž text začíná s tokenem od **seznam tokenů**, **seznamu úkolů** komentáře jako nová položka se zobrazí pokaždé, když je soubor otevřen pro úpravy. Můžete kliknout na to **seznamu úkolů** položky můžete přejít přímo na řádku komentáře v kódu. Další informace najdete v tématu [pomocí seznamu úkolů](../../ide/using-the-task-list.md).  
  
 seznam tokenů  
 Zobrazí seznam tokenů a umožňuje přidat nebo odebrat vlastní tokeny. Tokeny komentáře se rozlišuje velikost písmen v jazyce Visual C# a Visual C++, ale ne v jazyce Visual Basic.  
  
> [!NOTE]
> Pokud nezadáte požadovaný token, přesně tak, jak se zobrazuje v **seznam tokenů**, úkolu komentář se nezobrazí v **seznamu úkolů**.  
  
 Priorita  
 Nastaví prioritu úlohy, které používají vybraný token. Komentáře k úkolu, které začínají s tímto tokenem jsou automaticky přiřazeny určené priority v **seznamu úkolů**.  
  
 Název  
 Zadejte řetězec tokenu. Díky tomu **přidat** tlačítko. Na **přidat**, tento řetězec je součástí **seznam tokenů**, a komentáře, které začínají s tímto názvem se zobrazí v **seznamu úkolů**.  
  
 Přidejte  
 Povolený při zadání nového **název**. Klikněte na tlačítko Přidat nový řetězec tokenu pomocí zadaných hodnot **název** a **Priority** pole.  
  
 Odstranit  
 Chcete odstranit vybraný token z, klikněte **seznam tokenů**. Nelze odstranit výchozí token komentář.  
  
 Změna  
 Kliknutím provést změny existujícího tokenu pomocí zadaných hodnot **název** a **Priority** pole.  
  
> [!NOTE]
> Nelze přejmenovat nebo odstranit výchozí token komentář, ale můžete změnit jeho úroveň priority.  
  
## <a name="see-also"></a>Viz také  
 [Pomocí seznamu úkolů](../../ide/using-the-task-list.md)   
 [Nastavení záložek v kódu](../../ide/setting-bookmarks-in-code.md)   
 [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)
