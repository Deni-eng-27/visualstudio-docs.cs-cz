---
title: Podmínky nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, conditions
- conditions [MSBuild]
ms.assetid: 9d7aa308-b667-48ed-b4c9-a61e49eb0a85
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1070483e492bbbf6cc9f6e9f4a8f4b225f2b74b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842458"
---
# <a name="msbuild-conditions"></a>Podmínky nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podporuje konkrétní sadu podmínek, které lze použít všude, kde `Condition` atribut je povolen. Následující tabulka vysvětluje tyto podmínky.

|Podmínka|Popis|
|---------------|-----------------|
|'`stringA`' == '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` rovná `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|
|'`stringA`' != '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` není roven `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|
|\<, >, \<=, >=|Číselné hodnoty z operandů vyhodnotí. Vrátí `true` Pokud relační vyhodnocení má hodnotu true. Operandy musí vyhodnotit na desítkové nebo šestnáctkové číslo. Šestnáctková čísla musí začínat řetězcem "0 x". **Poznámka:**  V kódu XML znaky `<` a `>` musí být uvozeny řídicími znaky. Symbol `<` je vyjádřena jako `&lt;`. Symbol `>` je vyjádřena jako `&gt;`.|
|Existuje ("`stringA`")|Vyhodnotí jako `true` Pokud soubor nebo složka s názvem `stringA` existuje.<br /><br /> Příklad:<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|
|HasTrailingSlash('`stringA`')|Vyhodnotí jako `true` Pokud zadaný řetězec obsahuje buď koncové zpětné lomítko (\\) nebo předávání znak lomítka (/).<br /><br /> Příklad:<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|
|!|Vyhodnotí jako `true` Pokud operand je vyhodnocen jako `false`.|
|A|Vyhodnotí jako `true` Pokud mají oba operandy `true`.|
|Nebo|Vyhodnotí jako `true` Pokud se alespoň jeden z operandů vyhodnotí jako `true`.|
|()|Seskupovací mechanismus, který se vyhodnotí `true` Pokud výrazy obsažené uvnitř `true`.|
|$if$ (% výrazem %), $else$, $endif$|Kontroluje, zda zadaný `%expression%` shoduje s hodnotou řetězce parametr předaný vlastní šablony. Pokud `$if$` podmínka vyhodnocena jako `true`, pak jeho příkazy spuštění; v opačném případě `$else$` podmínka je zaškrtnuté políčko. Pokud `$else$` podmínka je `true`, pak jeho příkazy spuštění; v opačném případě `$endif$` podmínka ukončení vyhodnocení výrazu.<br /><br /> Příklady využití naleznete v tématu [logiky parametr šablony projektu/položky sady Visual Studio](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [Podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md)
- [Návod: Vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)
