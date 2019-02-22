---
title: Referenční dokumentace schématu VSCT XML | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c2643c88eaf133d41fba7a8112f9b92150be3148
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684634"
---
# <a name="vsct-xml-schema-reference"></a>Referenční dokumentace schématu VSCT XML
Poskytuje tabulku elementy schématu tabulky kompilátoru příkaz, povolené podřízených elementů a atributů pro každý.

 Soubor konfigurace (.vsct) založený na formátu XML příkaz tabulka definuje příkaz prvky, které poskytuje VSPackage integrovaného vývojového prostředí (IDE). Tyto prvky patří položek nabídky, nabídky, panely nástrojů a pole se seznamem.

> [!NOTE]
>  Kompilátor VSCT lze spustit v souboru .vsct preprocesor. Protože to je obvykle zahrnuje C++ preprocesoru, že můžete definovat a makra, které mají stejnou syntaxi, která se používá v souborech C++. Příklady jsou součástí .vsct souboru, který **nový projekt** průvodcem pro projekt VSPackage.

## <a name="optional-elements"></a>Volitelné prvky
 Některé VSCT prvky jsou volitelné. Pokud `Parent` argument nezadá, Group_Undefined:0 bude možné implicitní. Pokud `Icon` argument nezadáte, bude mlčky předpokládané guidOfficeIcon:msotcidNoIcon. Když je definována klávesovou zkratku, emulace, která se obvykle nepoužívá, je volitelný.

 Rastrový obrázek položky může být vložen v době kompilace, tak, že zadáte umístění pruhu rastrového obrázku v `href` argument. Vymazat bitmapu je zkopírované během sloučení spíše než extrahovaná ze zdroje knihovny DLL. Když `href` argument je k dispozici, `usedList` volitelně argument a všechny sloty v pruhu rastrového obrázku jsou považovány za použít.

 Všechny hodnoty GUID a ID musí být definován pomocí symbolické názvy. Tyto názvy mohou být definovány v souborech hlaviček nebo VSCT \<symboly > oddíly. Symbolické názvy musí být místní, zahrnuté prostřednictvím \<zahrnout > elementy, nebo odkazovaná \<Extern > elementy. Symbolický název je importován z hlavičky souboru zadaného v \<Extern > elementu, jestliže postupuje jednoduchý vzorec #define hodnota symbolu. Hodnota může být další symbol, tak dlouho, dokud tento symbol byla dříve definovaná. Identifikátor GUID definice musí mít formát OLE nebo C++. ID hodnoty mohou být desítkové číslice nebo šestnáctkové číslice, před kterými je 0 x, jak je znázorněno v následující řádky:

- {6D484634-E53D-4a2c-ADCB-55145C9362C8}

- { 0x6d484634, 0xe53d, 0x4a2c, { 0xad, 0xcb, 0x55, 0x14, 0x5c, 0x93, 0x62, 0xc8 } }

  Komentáře XML mohou být použity, ale operace round-trip grafické uživatelské rozhraní (GUI) nástroje může zrušit je. Obsah \<Poznámka > elementy zaručeno udržovat bez ohledu na formát.

## <a name="schema-hierarchy"></a>Hierarchie schémat
 Souboru .vsct má následující hlavní prvky.

- [Commandtable – element](../extensibility/commandtable-element.md)

- [Extern – element](../extensibility/extern-element.md)

- [Prvek direktivy include](../extensibility/include-element.md)

- [Define – element](../extensibility/define-element.md)

- [Commands – element](../extensibility/commands-element.md)

- [Commandplacements – element](../extensibility/commandplacements-element.md)

- [Visibilityconstraints – element](../extensibility/visibilityconstraints-element.md)

- [Keybindings – element](../extensibility/keybindings-element.md)

- [Usedcommands – element](../extensibility/usedcommands-element.md)

- [Nadřazený element](../extensibility/parent-element.md)

- [Icon – element](../extensibility/icon-element.md)

- [Strings – element](../extensibility/strings-element.md)

- [Command Flag – element](../extensibility/command-flag-element.md)

- [Symbols – element](../extensibility/symbols-element.md)

- [Podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md)

## <a name="see-also"></a>Viz také:
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Směrování příkazů v balíčcích VSPackage](../extensibility/internals/command-routing-in-vspackages.md)