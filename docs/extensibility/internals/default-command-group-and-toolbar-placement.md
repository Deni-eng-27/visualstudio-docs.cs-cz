---
title: Výchozí příkaz, skupiny a umístění nástrojů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands [Visual Studio], default groups
- toolbars [Visual Studio], default
- commands [Visual Studio], default editor
- command groups
- commands [Visual Studio], default IDE
- commands [Visual Studio], default product
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c4445531b48b35de9b47d1b68478cf344bf31d2d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351656"
---
# <a name="default-command-group-and-toolbar-placement"></a>Výchozí umístění příkazu, skupiny a nástrojů
Sjednocení produktu a stability, uživatelské rozhraní zobrazí určité skupiny příkazů ve výchozím nastavení, a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] obsahuje definice pro příkazy a skupin. Rozšíření VSPackages můžete taky použít standardní příkazy a skupin.

 Příkaz výchozích spadají do tří kategorií: Integrované vývojové prostředí příkazy, příkazy produktu a příkazů editoru.

## <a name="default-ide-commands"></a>Výchozí prostředí IDE příkazy
 Integrované vývojové prostředí nástrojů výchozí obsahuje příkazy, které sdílí všechny produkty, které jsou obsaženy v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Patří mezi ně příkazy týkající se operací obecného projektu, například **Uložit** příkazu a **přidat položku** příkazu. Rozšíření VSPackages by neměl přidat k nebo odečíst od tento panel nástrojů s jednou výjimkou: Pokud produkt nebo VSPackage přidá nového okna nástroje, pak v okně přidaly do seznamu k dispozici nástroj windows na **zobrazení** nabídky. Vlastní panel nástrojů můžete přidat nové produkty nebo rozšíření VSPackages.

## <a name="default-product-commands"></a>Výchozí produktu příkazy
 Integrované vývojové prostředí s vlastní výchozí panel nástrojů, která obsahuje důležité a často používané příkazy můžete zadat jednotlivé produkty. Doporučujeme, ale používat stávající nabídky a panely nástrojů, kdykoli je to možné a doplnit je panelů specifické úkoly podle potřeby.

 Pole Priorita pro panel nástrojů určuje jeho umístění řádku. Nulové priority umístí panelu nástrojů na třetím řádku (řádek 3), pod nabídek (řádek 1) a **standardní** nástrojů (řádek 2). Proto se zobrazí na řádku panelů nástrojů (Priorita + 3). Následné panely nástrojů jsou umístěny na stejném řádku, pokud je volného místa; v opačném případě se se automaticky přesouvají na dalším řádku.

## <a name="default-editor-commands"></a>Výchozí editor příkazy
 VSPackage, která poskytuje vlastní editor by měla poskytnout výchozí nástrojů, který obsahuje nejdůležitější a často používané příkazy v tomto editoru. Zobrazit panel nástrojů editoru při editoru aktivní a skryt, pokud editor není aktivní. Tento přehled slouží v `VisibilityConstraints` elementu *.vsct* souboru.

 Panely nástrojů editoru by měl být umístěn pod integrované vývojové prostředí a produktu panely nástrojů.

## <a name="see-also"></a>Viz také:
- [Příkazy definované prostředím IDE, nabídky a skupiny](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)