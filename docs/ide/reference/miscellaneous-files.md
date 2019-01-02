---
title: Ostatní soubory
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.newfile
- VS.OpenWith
- MiscellaneousFilesProject
helpviewer_keywords:
- solutions, miscellaneous files
- builds [Visual Studio], miscellaneous files
- standalone files
- Solution Explorer, miscellaneous files
- Miscellaneous Files folder
- files [Visual Studio], outside of containers
- files [Visual Studio], Miscellaneous Files folder
ms.assetid: 5b96640b-8efe-48a4-8d0a-1ae3f9587e44
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d764cea7992a9833bd8bddde8432388aebbc994
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867157"
---
# <a name="miscellaneous-files"></a>Ostatní soubory
Můžete chtít použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] editory pracovat nezávisle na soubory z projektu nebo řešení. Když máte řešení otevřené, můžete otevřít a upravit soubory bez jejich přidání do řešení nebo projektu. Soubory, které chcete pracovat s nezávisle na kontejnery se nazývají různé soubory. Různé soubory jsou externí vzhledem k řešení a projektů, nejsou zahrnuty v sestavení a nemůže být součástí řešení pod správou zdrojových kódů.

 Otevírání souborů nezávisle z kontejneru je užitečné pro celou řadu důvodů. Můžete mít soubor, který chcete zobrazit při vývoji řešení založené na projektu, ale není celočíselný k vývoji tohoto řešení. Běžné příklady vývojové poznámky nebo pokynů, schéma databáze a klipů kódu. Kromě toho můžete vytvořit samostatný soubor.

 ![Projekty řešení](../../ide/reference/media/projects_solutions_misc.gif)

 Průzkumník řešení zobrazíte složku různé soubory pro soubory, když jsou povolené možnosti pro složku. Možnosti můžete nastavit [dokumenty, prostředí, dialogové okno Možnosti](../../ide/reference/documents-environment-options-dialog-box.md). Po zavření souboru různé není přidružené žádné konkrétní řešení nebo projektu, pokud možnost není povolena pro, který také.

 Ve složce ostatní soubory představuje soubory jako odkazy. I když tato složka není součástí řešení, když otevřete řešení, některé nebo všechny ostatní soubory, které byly otevřeny při posledním zavření řešení jsou znovu otevřít, v závislosti na nastavení pro složku.

> [!NOTE]
> Některé soubory, které nejsou uvedeny ve složce ostatní soubory jsou soubory, které nelze upravovat v rámci rozhraní IDE, jako jsou soubory ZIP a DOC soubory. Integrované vývojové prostředí nebude sledovat soubory, které lze upravovat pouze prostřednictvím externího editoru.


## <a name="commands-available-in-the-ide"></a>Příkazy, které jsou k dispozici v integrovaném vývojovém prostředí
 Nabídky, panely nástrojů a příkazy obsahují mění v závislosti na formát souboru je otevřít. Když otevřete textový soubor, například se zobrazí panelu nástrojů textového editoru a jeho příkazy jsou k dispozici. Když potom otevřete soubor schématu XML, zobrazí se panel nástrojů schématu XML. Při úpravách schématu XML, nejsou k dispozici příkazy nástrojů textového editoru (nebo na panelu nástrojů, samotné). Schéma XML je aktivní okno a v důsledku toho se kontext aktuálního výběru. Při přepínání mezi soubor projektu a soubor různé všechny příkazy související s projektem zmizí a zobrazí pouze ty, které jsou přímo souvisí s různé souboru.

## <a name="folder-display-options"></a>Možnosti zobrazení složky
 Možnosti zobrazení pro různé složky můžete nastavit tak, aby složka se zobrazí i v případě, že všechny ostatní soubory ještě nebyl otevřen. Soubor řešení nedokáže spravovat trvale seznam různých souborů. Používá volitelná funkce, které umožňuje mějte na paměti na uživatele naposledy použité (MRU) seznam souborů.

## <a name="see-also"></a>Viz také

- [Řešení a projekty](../../ide/solutions-and-projects-in-visual-studio.md)
- [Dokumenty, Prostředí, dialogové okno Možnosti](../../ide/reference/documents-environment-options-dialog-box.md)