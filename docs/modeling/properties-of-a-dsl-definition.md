---
title: Vlastnosti definice DSL
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee23e15e6cc389ea5a8bdcdd793648365d08c30d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85532299"
---
# <a name="properties-of-a-dsl-definition"></a>Vlastnosti definice DSL
Vlastnosti DslDefinition definují vlastnosti definice *jazyka specifického pro doménu* , jako je například číslování verzí. Vlastnosti DslDefinition se zobrazí v okně **vlastnosti** , když kliknete na otevřenou oblast diagramu v *Návrháři jazyka specifického pro doménu*.

 Další informace najdete v tématu [Definování jazyka specifického pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak tyto vlastnosti používat, najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).

 DslDefinition má vlastnosti v následující tabulce:

|Vlastnost|Popis|Výchozí|
|-|-|-|
|Modifikátor přístupu|Určuje, jestli je modifikátor přístupu pro doménovou třídu veřejný nebo interní.|public|
|Vlastní atributy|Vlastní definované atributy pro doménovou třídu.<br /><br /> **Poznámka:** K přidání atributu použijte tlačítko Procházet.|\<none>|
|Název společnosti|Název aktuálního názvu společnosti v registru systému.|Název aktuální společnosti|
|Název|Název této doménové třídy|Aktuální název|
|Obor názvů|Obor názvů přidružený k této doménové třídě|Aktuální obor názvů|
|Identifikátor GUID balíčku|Identifikátor GUID balíčku sady Visual Studio vygenerovaného pro tento DSL|\<none>|
|Obor názvů balíčku|Obor názvů pro balíček sady Visual Studio vygenerovaný pro tento DSL|\<none>|
|Název produktu|Název produktu, který se zaregistruje pro balíček sady Visual Studio vygenerovaný pro tento DSL|\<none>|
|Poznámky|Poznámky přidružené k této doménové třídě|\<none>|
|Popis|Popis této doménové třídy|\<none>|
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři pro tuto doménovou třídu.|\<none>|
|Klíčové slovo Help|Klíčové slovo Help přidružené k této doménové třídě|\<none>|
|Sestavení|Číslo přírůstkového sestavení pro tuto definici jazyka specifického pro doménu.|0|
|Hlavní verze|Přírůstkové hlavní číslo buildu pro tuto definici jazyka specifického pro doménu.|1|
|Podverze|Přírůstkové číslo sestavení pro tuto definici jazyka specifického pro doménu.|0|
|Revize|Číslo buildu přírůstkové revize pro tuto definici jazyka specifického pro doménu.|0|

## <a name="see-also"></a>Viz také

- [Glosář Nástroje DSL](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)