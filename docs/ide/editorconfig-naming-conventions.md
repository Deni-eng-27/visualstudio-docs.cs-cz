---
title: Soubory .NET pojmenování konvence pro EditorConfig
ms.date: 11/20/2017
ms.topic: reference
helpviewer_keywords:
- naming conventions [EditorConfig]
- EditorConfig naming conventions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4385ad73b29f1266bb368a781da11279f887942b
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65847363"
---
# <a name="net-naming-conventions-for-editorconfig"></a>Zásady vytváření názvů .NET pro EditorConfig

Konvence pojmenování se týkají názvy prvků kódu, jako jsou třídy, vlastnosti a metody. Můžete například určit, že musí velkými písmeny veřejné členy nebo, že musí asynchronních metod končí slovem "Async". Tato pravidla můžete vynutit tak, že zadáte je do [souboru .editorconfig](../ide/create-portable-custom-editor-options.md). Pojmenování porušení pravidel se zobrazí v **seznam chyb** nebo jako návrh pod názvem, v závislosti na závažnosti se rozhodnete pro pravidlo. Není nutné pro sestavení projektu, chcete-li zobrazit porušení.

Zásady vytváření názvů by měl být seřazené od specifické pro většinu nejméně na konkrétní EditorConfig souboru. Je první pravidlo došlo k, který lze použít pouze pravidlo, které se použije. Nicméně pokud existuje více pravidel *vlastnosti* se stejným názvem, naposledy nalezena vlastnost s tímto názvem má přednost před. Další informace najdete v tématu [souborů hierarchie a Priorita](create-portable-custom-editor-options.md#file-hierarchy-and-precedence).

Pro každé zásady vytváření názvů je nutné zadat symboly, které se vztahuje na, styl pojmenování a závažnost pro vynucení konvence, pomocí vlastností popsaných níže. Vlastnosti pořadí není důležité.

Pokud chcete začít, vyberte záhlaví pravidla pojmenování, kterou budete používat ve všech vlastností, které jsou potřeba k plně popis pravidla. Například `public_members_must_be_capitalized` je dobré, popisný název pro pravidlo pro pojmenování. Budeme odkazovat na název, vyberte jako **< namingRuleTitle\>**  v následujících částech.

## <a name="symbols"></a>Symboly

Nejprve určete skupinu symboly, které chcete použít pravidlo pro pojmenování pro. Tato vlastnost má následující formát:

`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`

Zadejte název skupiny symbolů tak, že nahradíte **< symbolTitle\>**  hodnotu popisný název, třeba `public_symbols`. Budete používat **< symbolTitle\>**  v názvech tři vlastnosti, které popisují hodnotu, která symboly pravidlo platí pro (druhy symbolů, úrovní přístupu a modifikátory).

### <a name="kinds-of-symbols"></a>Druhy symbolů

K popisu druh symboly pro pojmenování pravidlo použít, zadejte vlastnost v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = <values>`

Následující seznam obsahuje povolených hodnot, a můžete zadat více hodnot oddělených čárkami.

- \* (Tato hodnota slouží k určení všechny symboly)
- – obor názvů
- třída
- struct 
- rozhraní
- enum
- property
- – metoda
- pole
- event
- delegát
- parametr
- type_parameter
- místní
- local_function

### <a name="accessibility-levels-of-symbols"></a>Úrovně přístupnosti symbolů

K popisu úrovní přístupu symbolů má pravidlo pro pojmenování použít, zadejte název vlastnosti v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = <values>`

Následující seznam obsahuje povolených hodnot, a můžete zadat více hodnot oddělených čárkami.

- \* (Tato hodnota slouží k určení všech úrovní přístupu)
- public
- interní nebo typu friend
- private
- protected
- chráněné\_interní nebo protected_friend
- privátní\_chráněné
- místní

   `local` Úrovni přístupu platí pro symboly definované v rámci metody. Je užitečné pro definování zásady vytváření názvů pro symboly, jehož usnadnění nelze zadat v kódu. Pokud zadáte například `applicable_accessibilities = local` na zásady vytváření názvů pro konstanty (`required_modifiers = const`), se pravidlo vztahuje pouze na konstanty definované v rámci metody a ne těch, které jsou definovány v rámci typu.

   ```csharp
   class TypeName
   {
     // Constant defined in a type.
     const int X = 3;

     void Method()
     {
       // Constant defined in a method with "local" accessibility.
       const int Y = 4;
     }
   }
   ```

### <a name="symbol-modifiers-optional"></a>Symbol modifikátory (volitelné)

K popisu modifikátory symboly chcete pravidlo pro pojmenování použít, zadejte název vlastnosti v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.required_modifiers = <values>`

Následující seznam obsahuje povolené hodnoty (oddělte čárkou více hodnot):

- `abstract` Nebo `must_inherit`
- `async`
- `const`
- `readonly`
- `static` Nebo `shared`

   > [!NOTE]
   > Pokud máte pravidlo pro pojmenování pro `static` nebo `shared` symboly, budou také použity na `const` symboly, protože jsou implicitně statické. Pokud nechcete, aby `static` pravidlo pro pojmenování vyrovnat `const` symboly, vytvořte samostatné pravidlo pro pojmenování pro `const` symboly.

Pravidlo pro pojmenování shoduje s podpisy, které mají *všechny* modifikátory podle `required_modifiers`. Pokud ji vynecháte, je použita výchozí hodnota je seznam prázdný, to znamená, jsou požadovány pro shodu bez konkrétních parametrů. To znamená, že symbolu modifikátory nemají žádný vliv na tom, zda toto pravidlo se použije.

> [!TIP]
> Nezadávejte hodnotu `*` pro `required_modifiers`. Místo toho jednoduše vynechejte `required_modifiers` vlastnost zcela a pravidlo pro pojmenování má platit pro jakýkoli druh modifikátor.

## <a name="style"></a>Styl

Teď, když jsme identifikovali symboly, které chcete použít pravidlo pro pojmenování pro skupiny, popisujeme musí styl pojmenování. Styl může být, že název obsahuje určité předponu nebo příponu určité nebo jednotlivých slov v názvu jsou odděleny určitých znaků. Můžete také určit styl malá a velká písmena. Vlastnost stylu má následující formát:

`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`

Zadejte styl název nahrazením **< styleTitle\>**  hodnotu popisný název, třeba `first_word_upper_case_style`. Budete používat **< styleTitle\>**  hodnotu názvy vlastností, které popisují pojmenování styl (předpona, příponu, word oddělovací znak a malá a velká písmena). Použití jednoho nebo více z těchto vlastností, které popisují vašemu stylu.

### <a name="require-a-prefix"></a>Vyžadují předponu

Chcete-li určit, že názvy symbolů musí začínat určitých znaků, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.required_prefix = <prefix>`

### <a name="require-a-suffix"></a>Požadavek na zadání přípony

Chcete-li určit, že názvy symbolů musí končit určitých znaků, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.required_suffix = <suffix>`

### <a name="require-a-certain-word-separator"></a>Vyžadovat určité slovo oddělovač

Chcete-li určit, že jednotlivá slova v názvech symbol, musí se oddělit určité znakem, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.word_separator = <separator character>`

### <a name="require-a-capitalization-style"></a>Vyžadovat Styl malá a velká písmena

Tuto vlastnost použijte k určení stylu konkrétní malá a velká písmena pro názvy symbolů:

`dotnet_naming_style.<styleTitle>.capitalization = <value>`

Povolené hodnoty této vlastnosti jsou:

- pascal_case
- camel_case
- first\_word_upper
- všechny\_horní
- all_lower

> [!NOTE]
> Styl malá a velká písmena musíte zadat jako součást vaší pojmenování styl, jinak může vašemu stylu pojmenování ignorovat.

## <a name="severity"></a>Severity

K popisu závažnost porušení pravidla pojmenování, určete vlastnost v následujícím formátu:

`dotnet_naming_rule.<namingRuleTitle>.severity = <value>`

V následující tabulce jsou uvedeny hodnoty povolenou závažnosti a jejich význam:

Severity | Efekt
------------ | -------------
žádné nebo tiché | Když se tento styl nedodrží, nezobrazují žádné uživatele. automaticky generovaný kód se však řídí tímto stylem.
Návrh | Když se tento styl nedodrží, zobrazit uživateli jako návrh, jako základní tečky v prvních dvou znacích. V době kompilace nemá žádný vliv.
upozornění | Když tento styl nedodrží, zobrazí upozornění kompilátoru v **seznam chyb**.
error | Když tento styl nedodrží, zobrazit chybu kompilátoru ve **seznam chyb**.

> [!NOTE]
> Nemáte k sestavení projektu, chcete-li zobrazit názvy porušení pravidel. Se zobrazují jako kód je upravovat, buď **seznam chyb** nebo jako návrh.

## <a name="example"></a>Příklad

Následující *.editorconfig* soubor obsahuje zásady vytváření názvů, který určuje, že veřejné vlastnosti, metody, pole, události a delegáti musí být velkými písmeny. Všimněte si, že tyto zásady vytváření názvů určuje více druhů symbol, který chcete použít pravidlo, pomocí čárky k oddělení hodnoty.

```ini
# Public members must be capitalized (public_members_must_be_capitalized)
[*.{cs,vb}]
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

Následující snímek obrazovky ukazuje efekt tyto zásady vytváření názvů v editoru. Dvě veřejné proměnné, které byly pojmenovány bez malá a velká písmena první písmeno. Je `const`, a jeden je `readonly`. Vzhledem k tomu, že pravidlo pro pojmenování platí pouze pro `readonly` symboly, pouze `readonly` proměnná ukazuje návrh pravidlo pojmenování.

![Návrh pravidla pojmenování](media/editorconfig-naming-rule-suggestion.png)

Teď Změníme závažnost porušení na `warning`:

```ini
dotnet_naming_rule.public_members_must_be_capitalized.severity = warning
```

Pokud ho zavřete a znovu otevřít souboru s kódem, místo toho návrhů v části porušení názvu, abyste se zobrazí zelenou vlnovkou a upozornění v **seznam chyb**:

![Pojmenování upozornění pravidla](media/editorconfig-naming-rule-warning.png)

## <a name="see-also"></a>Viz také:

- [Jazyk a zásady formátování rozhraní .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Vytvoření přenosné vlastního editoru](../ide/create-portable-custom-editor-options.md)
- [.NET compiler Platform .editorconfig file](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
