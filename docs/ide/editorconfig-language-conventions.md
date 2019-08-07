---
title: Jazykové konvence rozhraní .NET pro EditorConfig
ms.date: 07/17/2019
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7b88824e6be7dbb216aa14ca9a22fd692474ec2f
ms.sourcegitcommit: a124076dfd6b4e5aecda4d01984fee7b0c034745
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68787425"
---
# <a name="language-conventions"></a>Konvence jazyka

Jazykové konvence pro EditorConfig v aplikaci Visual Studio spadají do dvou kategorií: ty, které se C#vztahují na Visual Basic a a C# ty, které jsou specifické. Jazykové konvence mají vliv na to, jak se používají různé aspekty programovacího jazyka, například modifikátory a závorky.

> [!TIP]
> - Pomocí odkazu **v tomto článku** můžete přejít na jiné části stránky.
> - Chcete-li zobrazit příklady kódu v upřednostňovaném programovacím jazyce, vyberte jej pomocí nástroje pro výběr jazyka v pravém horním rohu okna prohlížeče.
>
>   ![Ovládací prvek pro výběr jazyka kódu](media/code-language-picker.png)

## <a name="rule-format"></a>Formát pravidla

Pravidla pro jazykové konvence mají následující obecný formát:

`option_name = value:severity`

Pro každou jazykovou konvenci zadáte hodnotu, která definuje, kdy nebo kdy chcete styl preferovat. `true` Mnoho pravidel přijímá hodnotu (Tento styl upřednostňuje) nebo `false` (nepreferovat tento styl); `when_on_single_line` ostatní akceptují hodnoty jako nebo `never`. Druhá část pravidla určuje **závažnost**.

### <a name="severity"></a>severity

Závažnost jazykové konvence určuje úroveň, na které se má tento styl vyhovět. V následující tabulce jsou uvedeny možné hodnoty závažnosti a jejich důsledky:

severity | Efekt
:------- | ------
`none` | Nezobrazovat uživateli žádné údaje, pokud je toto pravidlo porušeno. Funkce pro generování kódu generují kód v tomto stylu, ale. Pravidla se `none` závažností se nikdy neobjevují v nabídce **rychlé akce a** refaktoringu. Ve většině případů se to považuje za "zakázané" nebo "ignorované".
`silent`(také `refactoring` v aplikaci Visual Studio 2017 verze 15,8 a novější) | Nezobrazovat uživateli žádné údaje, pokud je toto pravidlo porušeno. Funkce pro generování kódu generují kód v tomto stylu, ale. Pravidla se `silent` závažností se účastní vyčištění i v nabídce **rychlé akce a** refaktoringy.
`suggestion` | Když je toto pravidlo stylu porušeno, zobrazte ho uživateli jako návrh. Návrhy se zobrazí jako tři šedé tečky pod prvními dvěma znaky.
`warning` | Při porušení tohoto pravidla stylu zobrazit upozornění kompilátoru.
`error` | Při porušení tohoto pravidla stylu zobrazit chybu kompilátoru.

## <a name="net-code-style-settings"></a>Nastavení stylu kódu .NET

Pravidla stylu v této části platí pro C# i Visual Basic.

- [Kvalifikátory "This." a "já"](#this-and-me)
  - for_field kvalifikace\_\_stylu\_dotnet
  - dotnet\_style\_qualification\_for_property
  - for_method kvalifikace\_\_stylu\_dotnet
  - for_event kvalifikace\_\_stylu\_dotnet
- [Klíčová slova jazyka namísto názvů typů rozhraní pro odkazy na typy](#language-keywords)
  - \_\_předdefinovaný\_Typstyludotnetpro\_lokální hodnotyparameters_members\_\_
  - dotnet\_style\_predefined\_type\_for\_member_access
- [Předvolby modifikátoru](#normalize-modifiers)
  - styl\_dotnet\_vyžaduje\_accessibility_modifiers.
  - csharp\_preferred\_modifier_order
  - visual\_basic\_preferred\_modifier_order
  - pole\_jen\_pročtení\_stylu dotnet
- [Předvolby závorek](#parentheses-preferences)
  - \_kulaté\_\_\_závorky\_stylu dotnet v aritmetických binárních operátorech\_
  - \_v\_jiných\_\_binárníchoperátorechsevestyludotnetnaplnízávorky.\_\_
  - \_kulaté\_\_závorky\_stylu dotnetv\_jiných operátorech
  - \_kulaté\_\_\_závorky\_stylu dotnet v relačních binárních operátorech\_
- [Předvolby na úrovni výrazu](#expression-level-preferences)
  - dotnet\_style\_object_initializer
  - dotnet\_–\_styl collection_initializer
  - dotnet\_–\_stylexplicitní\_tuple_names
  - styl\_dotnet\_preferovat\_odvozenoutuple_names\_
  - styl\_dotnet\_preferovat\_odvození\_anonymního\_typumember_names\_
  - dotnet\_style\_prefer\_auto\_properties
  - styl\_dotnetpreferovat\_jehodnotanull\_kontrolynad\_referenčnímetodourovnosti\_.\_\_\_\_
  - styl\_dotnet–\_preferovatpodmíněný\_výraz\_nadpřiřazením\_\_
  - styl\_dotnet–\_preferovatpodmíněný\_výraz\_při návratu\_\_
  - styl\_dotnetpreferovat\_složenépřiřazení\_\_
- [Předvolby kontroly "null"](#null-checking-preferences)
  - dotnet\_style\_coalesce_expression
  - dotnet\_style\_null_propagation

### <a name="this-and-me"></a>"This." a "já". kvalifikátory

Toto pravidlo stylu lze použít pro pole, vlastnosti, metody nebo události. Hodnota **true** znamená, že se symbol kódu bude považovat `this.` za v C# `Me.` Visual Basic. Hodnota **false** znamená, že by element Code _neměl_ být s `this.` nebo. `Me.`

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="dotnet_style_qualification_for_field"></a>for_field kvalifikace\_\_stylu\_dotnet

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_field |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat pole, která mají být `this.` v C# nebo `Me.` v Visual Basic<br /><br />`false`– Preferovat pole, která _nemají_ být uvozena `this.` nebo`Me.` |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

#### <a name="dotnet_style_qualification_for_property"></a>dotnet\_style\_qualification\_for_property

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_property |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Upřednostnit vlastnosti, které mají být v `this.` C# nástroji nebo `Me.` v Visual Basic<br /><br />`false`-Upřednostnit vlastnosti, které _nemají_ být uvozeny `this.` nebo`Me.` |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

#### <a name="dotnet_style_qualification_for_method"></a>for_method kvalifikace\_\_stylu\_dotnet

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_method |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Preferovat metody, které mají být `this.` v C# nebo `Me.` Visual Basic.<br /><br />`false`-Preferovat metody, které _nemají_ být uvozeny `this.` nebo `Me.`. |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

#### <a name="dotnet_style_qualification_for_event"></a>for_event kvalifikace\_\_stylu\_dotnet

|||
|-|-|
| **Název pravidla** | dotnet_style_qualification_for_event |
| **ID pravidla** | IDE0003 a IDE0009 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Preferovat události, které mají být `this.` v C# nebo `Me.` Visual Basic.<br /><br />`false`-Preferovat události , které nemusejí být uvozeny `this.` nebo `Me.`. |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

### <a name="language-keywords"></a>Klíčová slova jazyka namísto názvů typů rozhraní pro odkazy na typy

Toto pravidlo stylu lze použít pro lokální proměnné, parametry metody a členy třídy nebo jako samostatné pravidlo pro typ výrazů přístupu členů. Hodnota **true** znamená preferovat klíčové slovo jazyka ( `int` například nebo `Integer`) namísto názvu typu (například `Int32`) pro typy, které mají klíčové slovo reprezentovat. Hodnota **false** znamená raději název typu místo klíčového slova Language.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="dotnet_style_predefined_type_for_locals_parameters_members"></a>\_\_předdefinovaný\_Typstyludotnetpro\_lokální hodnotyparameters_members\_\_

|||
|-|-|
| **Název pravidla** | dotnet_style_predefined_type_for_locals_parameters_members |
| **ID pravidla** | IDE0012 a IDE0014 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat klíčové slovo jazyka pro místní proměnné, parametry metody a členy třídy místo názvu typu, pro typy, které mají klíčové slovo k reprezentování<br /><br />`false`– Raději zadejte název typu pro lokální proměnné, parametry metody a členy třídy místo klíčového slova Language. |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

#### <a name="dotnet_style_predefined_type_for_member_access"></a>dotnet\_style\_predefined\_type\_for\_member_access

|||
|-|-|
| **Název pravidla** | dotnet_style_predefined_type_for_member_access |
| **ID pravidla** | IDE0013 a IDE0015 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat klíčové slovo jazyka pro výrazy přístupu členů namísto názvu typu, pro typy, které mají klíčové slovo, které je reprezentovat<br /><br />`false`– Raději jako název typu pro výrazy přístupu členů místo klíčového slova Language |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

### <a name="normalize-modifiers"></a>Předvolby modifikátoru

Pravidla stylu v této části se týkají předvoleb modifikátoru, včetně vyžadování modifikátorů přístupnosti, určení pořadí řazení požadovaného modifikátoru a vyžadování modifikátoru jen pro čtení.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion
dotnet_style_readonly_field = true:warning

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="dotnet_style_require_accessibility_modifiers"></a>styl\_dotnet\_vyžaduje\_accessibility_modifiers.

|||
|-|-|
| **Název pravidla** | dotnet_style_require_accessibility_modifiers |
| **ID pravidla** | IDE0040 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always`– Preferovat Modifikátory dostupnosti, které se mají zadat.<br /><br />`for_non_interface_members`– Upřednostnit Modifikátory dostupnosti, které mají být deklarovány s výjimkou členů veřejných rozhraní. (To je stejné jako **Always** a bylo přidáno pro budoucí kontrolu, pokud C# nástroj přidá výchozí metody rozhraní.)<br /><br />`never`– Nepreferovat Modifikátory dostupnosti, které se mají zadat<br /><br />`omit_if_default`– Upřednostnit Modifikátory dostupnosti, které mají být zadány s výjimkou případů, kdy jsou výchozím modifikátorem. |
| **Výchozí nastavení sady Visual Studio** | `for_non_interface_members:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.5 |

Příklady kódu:

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst = "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst = "constant";
}
```

#### <a name="csharp_preferred_modifier_order"></a>csharp_preferred_modifier_order

|||
|-|-|
| **Název pravidla** | csharp_preferred_modifier_order |
| **ID pravidla** | IDE0036 |
| **Příslušné jazyky** | C# |
| **Hodnoty** | Jeden nebo více C# modifikátorů, například `public`, `private`a`protected` |
| **Výchozí nastavení sady Visual Studio** | `public, private, protected, internal, static, extern, new, virtual, abstract, sealed, override, readonly, unsafe, volatile, async:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.5 |

- Pokud je toto pravidlo nastaveno na seznam modifikátorů, preferovat zadané řazení.
- Pokud je toto pravidlo vynecháno ze souboru, nedoporučujeme pořadí modifikátorů.

Příklady kódu:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

#### <a name="visual_basic_preferred_modifier_order"></a>visual_basic_preferred_modifier_order

|||
|-|-|
| **Název pravidla** | visual_basic_preferred_modifier_order |
| **ID pravidla** | IDE0036 |
| **Příslušné jazyky** | Visual Basic |
| **Hodnoty** | Jeden nebo více modifikátorů Visual Basic, například `Partial`, `Private`, a`Public` |
| **Výchozí nastavení sady Visual Studio** | `Partial, Default, Private, Protected, Public, Friend, NotOverridable, Overridable, MustOverride, Overloads, Overrides, MustInherit, NotInheritable, Static, Shared, Shadows, ReadOnly, WriteOnly, Dim, Const,WithEvents, Widening, Narrowing, Custom, Async:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.5 |

- Pokud je toto pravidlo nastaveno na seznam modifikátorů, preferovat zadané řazení.
- Pokud je toto pravidlo vynecháno ze souboru, nedoporučujeme pořadí modifikátorů.

Příklady kódu:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

#### <a name="dotnet_style_readonly_field"></a>dotnet_style_readonly_field

|||
|-|-|
| **Název pravidla** | dotnet_style_readonly_field |
| **ID pravidla** | IDE0044 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat, aby pole měla být `readonly` označenaC#() `ReadOnly` nebo (Visual Basic), pokud jsou pouze někdy přiřazena vložená nebo uvnitř konstruktoru<br /><br />`false`-Neurčovat, zda mají být pole označena pomocí `readonly` (C#) nebo `ReadOnly` (Visual Basic) |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15,7 |

Příklady kódu:

```csharp
// dotnet_style_readonly_field = true
class MyClass
{
    private readonly int _daysInYear = 365;
}
```

```vb
' dotnet_style_readonly_field = true
Public Class MyClass
    Private ReadOnly daysInYear As Int = 365
End Class
```

### <a name="parentheses-preferences"></a>Předvolby závorek

Pravidla stylu v této části se týkají předvoleb závorek, včetně použití závorek pro aritmetické, relační a další binární operátory.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent
```

#### <a name="dotnet_style_parentheses_in_arithmetic_binary_operators"></a>\_kulaté\_\_závorky\_stylu dotnet v aritmetických\_binary_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_arithmetic_binary_operators |
| **ID pravidla** | IDE0047 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity`– Preferovat kulaté závorky pro objasnění aritmetického `+`operátoru `<<`( `>>``*`, `&` `/`, `^` `%`, `|`, `-`,,,,,) priority<br /><br />`never_if_unnecessary``*`-Při aritmetickém operátoru (, `>>` `^`, `/` `-` `+` `%`,,, `<<`, `|`, `&`,,,,,,) nemusíte mít kulaté závorky. Priorita je zřejmá. |
| **Výchozí nastavení sady Visual Studio** | `always_for_clarity:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
var v = a + (b * c);

// dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
var v = a + b * c;
```

```vb
' dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
Dim v = a + (b * c)

' dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
Dim v = a + b * c
```

#### <a name="dotnet_style_parentheses_in_relational_binary_operators"></a>\_kulaté\_\_závorky\_stylu dotnet v relačních\_binary_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_relational_binary_operators |
| **ID pravidla** | IDE0047 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity`– Upřednostnit kulaté závorky k objasnění relačních operátorů `as`( `==``>`, `!=` `<`, `<=` `>=`,, `is`,,,) priority<br /><br />`never_if_unnecessary`– Nedoporučuje se závorky, když relační operátor (`>`, `<`, `<=` `>=`,, `is`, `as`, `==`, `!=`) je zřejmý. |
| **Výchozí nastavení sady Visual Studio** | `always_for_clarity:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
var v = (a < b) == (c > d);

// dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
var v = a < b == c > d;
```

```vb
' dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
Dim v = (a < b) = (c > d)

' dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
Dim v = a < b = c > d
```

#### <a name="dotnet_style_parentheses_in_other_binary_operators"></a>\_v\_jiných\_binary_operatorsch závorkách stylu\_dotnet\_

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_other_binary_operators |
| **ID pravidla** | IDE0047 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity`– Preferovat kulaté závorky pro vysvětlení jiné binární`&&`operátory `||`( `??`,,) priority<br /><br />`never_if_unnecessary`– Raději nepoužívejte závorky, pokud je jiná priorita binárního `||`operátoru (`&&`,, `??`) zřejmá. |
| **Výchozí nastavení sady Visual Studio** | `always_for_clarity:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
var v = a || (b && c);

// dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
var v = a || b && c;
```

```vb
' dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
Dim v = a OrElse (b AndAlso c)

' dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
Dim v = a OrElse b AndAlso c
```

#### <a name="dotnet_style_parentheses_in_other_operators"></a>\_kulaté\_závorky\_stylu\_dotnet v other_operators

|||
|-|-|
| **Název pravidla** | dotnet_style_parentheses_in_other_operators |
| **ID pravidla** | IDE0047 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `always_for_clarity`– Preferovat kulaté závorky k objasnění priority operátoru<br /><br />`never_if_unnecessary`-Preferovat, pokud je přednost operátoru, nemusíte mít závorky |
| **Výchozí nastavení sady Visual Studio** | `never_if_unnecessary:silent` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_parentheses_in_other_operators = always_for_clarity
var v = (a.b).Length;

// dotnet_style_parentheses_in_other_operators = never_if_unnecessary
var v = a.b.Length;
```

```vb
' dotnet_style_parentheses_in_other_operators = always_for_clarity
Dim v = (a.b).Length

' dotnet_style_parentheses_in_other_operators = never_if_unnecessary
Dim v = a.b.Length
```

### <a name="expression-level-preferences"></a>Předvolby na úrovni výrazu

Pravidla stylu v této části se týkají předvoleb na úrovni výrazu, včetně použití inicializátorů objektů, inicializátorů kolekcí, explicitních nebo odvozených názvů řazených kolekcí členů a odvozených anonymních typů.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_conditional_expression_over_assignment = true:suggestion
dotnet_style_prefer_conditional_expression_over_return = true:suggestion
dotnet_style_prefer_compound_assignment = true:suggestion
```

#### <a name="dotnet_style_object_initializer"></a>dotnet\_style\_object_initializer

|||
|-|-|
| **Název pravidla** | dotnet_style_object_initializer |
| **ID pravidla** | IDE0017 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat objekty, které se mají inicializovat pomocí inicializátorů objektů, pokud je to možné<br /><br />`false`-Preferovat objekty, které se *nemají* inicializovat pomocí inicializátorů objektů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

#### <a name="dotnet_style_collection_initializer"></a>dotnet\_–\_styl collection_initializer

|||
|-|-|
| **Název pravidla** | dotnet_style_collection_initializer |
| **ID pravidla** | IDE0028 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat kolekce, které se mají inicializovat pomocí inicializátorů kolekcí, pokud je to možné<br /><br />`false`-Preferovat kolekce, které se *nemají* inicializovat pomocí inicializátorů kolekcí |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

#### <a name="dotnet_style_explicit_tuple_names"></a>dotnet\_–\_stylexplicitní\_tuple_names

|||
|-|-|
| **Název pravidla** | dotnet_style_explicit_tuple_names |
| **ID pravidla** | IDE0033 |
| **Příslušné jazyky** | C#7.0 + a Visual Basic 15 + |
| **Hodnoty** | `true`-Preferovat názvy řazené kolekce členů k ItemXm vlastnostem<br /><br />`false`– Preferovat vlastnosti ItemX názvů řazených kolekcí členů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

#### <a name="dotnet_style_prefer_inferred_tuple_names"></a>styl\_dotnet\_preferovat\_odvozenoutuple_names\_

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_inferred_tuple_names |
| **ID pravidla** | IDE0037 |
| **Příslušné jazyky** | C#7.1 + a Visual Basic 15 + |
| **Hodnoty** | `true`-Preferovat odvozené názvy elementů řazené kolekce členů<br /><br />`false`-Preferovat explicitní názvy elementů řazené kolekce členů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15.6 |

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

```vb
' dotnet_style_prefer_inferred_tuple_names = true
Dim tuple = (name, age)

' dotnet_style_prefer_inferred_tuple_names = false
Dim tuple = (name:=name, age:=age)
```

#### <a name="dotnet_style_prefer_inferred_anonymous_type_member_names"></a>styl\_dotnet\_preferovat\_odvození\_anonymního\_typumember_names\_

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_inferred_anonymous_type_member_names |
| **ID pravidla** | IDE0037 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Preferovat odvozené názvy členů anonymního typu<br /><br />`false`-Preferovat explicitní názvy členů anonymního typu |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15.6 |

Příklady kódu:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };
```

```vb
' dotnet_style_prefer_inferred_anonymous_type_member_names = true
Dim anon = New With {name, age}

' dotnet_style_prefer_inferred_anonymous_type_member_names = false
Dim anon = New With {.name = name, .age = age}
```

#### <a name="dotnet_style_prefer_auto_properties"></a>dotnet\_style\_prefer\_auto\_properties

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_auto_properties |
| **ID pravidla** | IDE0032 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Preferovat vlastnosti autoproperties přes vlastnosti s privátními zálohovanými poli<br /><br />`false`-Preferovat vlastnosti pomocí soukromých zálohovacích polí přes autoproperties |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15,7 |

Příklady kódu:

```csharp
// dotnet_style_prefer_auto_properties = true
private int Age { get; }

// dotnet_style_prefer_auto_properties = false
private int age;

public int Age
{
    get
    {
        return age;
    }
}
```

```vb
' dotnet_style_prefer_auto_properties = true
Public ReadOnly Property Age As Integer

' dotnet_style_prefer_auto_properties = false
Private _age As Integer

Public ReadOnly Property Age As Integer
    Get
        return _age
    End Get
End Property
```

#### <a name="dotnet_style_prefer_is_null_check_over_reference_equality_method"></a>styl\_dotnetpreferovat\_jehodnotanull\_kontrolynad\_referenčnímetodourovnosti\_.\_\_\_\_

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_is_null_check_over_reference_equality_method |
| **ID pravidla** | IDE0041 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Raději použijte kontrolu null se porovnáváním vzorů.`object.ReferenceEquals`<br /><br />`false`– Preferovat `object.ReferenceEquals` pro kontrolu s hodnotou null se porovnáváním vzorů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15,7 |

Příklady kódu:

```csharp
// dotnet_style_prefer_is_null_check_over_reference_equality_method = true
if (value is null)
    return;

// dotnet_style_prefer_is_null_check_over_reference_equality_method = false
if (object.ReferenceEquals(value, null))
    return;
```

```vb
' dotnet_style_prefer_is_null_check_over_reference_equality_method = true
If value Is Nothing
    Return
End If

' dotnet_style_prefer_is_null_check_over_reference_equality_method = false
If Object.ReferenceEquals(value, Nothing)
    Return
End If
```

#### <a name="dotnet_style_prefer_conditional_expression_over_assignment"></a>dotnet\_style\_prefer\_conditional\_expression\_over_assignment

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_conditional_expression_over_assignment |
| **ID pravidla** | IDE0045 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Upřednostnit přiřazení s ternárním podmíněným příkazem if-else<br /><br />`false`– Preferovat přiřazení pomocí příkazu if-else přes Ternární podmíněný |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_prefer_conditional_expression_over_assignment = true
string s = expr ? "hello" : "world";

// dotnet_style_prefer_conditional_expression_over_assignment = false
string s;
if (expr)
{
    s = "hello";
}
else
{
    s = "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_assignment = true
Dim s As String = If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_assignment = false
Dim s As String
If expr Then
    s = "hello"
Else
    s = "world"
End If
```

#### <a name="dotnet_style_prefer_conditional_expression_over_return"></a>styl\_dotnetpreferovat\_podmíněný\_výraz over_return\_\_

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_conditional_expression_over_return |
| **ID pravidla** | IDE0046 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Preferovat návratové příkazy pro použití ternárního podmíněného příkazu if-else<br /><br />`false`-Preferovat návratové příkazy pro použití příkazu if-else nad Ternární podmínkou |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2017 verze 15.8 |

Příklady kódu:

```csharp
// dotnet_style_prefer_conditional_expression_over_return = true
return expr ? "hello" : "world"

// dotnet_style_prefer_conditional_expression_over_return = false
if (expr)
{
    return "hello";
}
else
{
    return "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_return = true
Return If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_return = false
If expr Then
    Return "hello"
Else
    Return "world"
End If
```

#### <a name="dotnet_style_prefer_compound_assignment"></a>styl\_dotnetpreferovat\_složenépřiřazení\_\_

|||
|-|-|
| **Název pravidla** | dotnet_style_prefer_compound_assignment |
| **ID pravidla** | IDE0054 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`-Preferovat výrazy [složeného přiřazení](/dotnet/csharp/language-reference/operators/assignment-operator#compound-assignment)<br /><br />`false`– Nepreferovat výrazy složeného přiřazení |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_prefer_compound_assignment = true
x += 1;

// dotnet_style_prefer_compound_assignment = false
x = x + 1;
```

```vb
' dotnet_style_prefer_compound_assignment = true
x += 1

' dotnet_style_prefer_compound_assignment = false
x = x + 1
```

### <a name="null-checking-preferences"></a>Předvolby pro kontrolu hodnoty null

Pravidla stylu v této části se týkají předvoleb pro kontrolu hodnoty null.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

#### <a name="dotnet_style_coalesce_expression"></a>dotnet\_style\_coalesce_expression

|||
|-|-|
| **Název pravidla** | dotnet_style_coalesce_expression |
| **ID pravidla** | IDE0029 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `true`– Upřednostnit hodnoty null slučovacích výrazů pro kontrolu ternárních operátorů<br /><br />`false`-Upřednostnit Ternární operátor zaškrtnutí na hodnoty null slučovacích výrazů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

#### <a name="dotnet_style_null_propagation"></a>dotnet\_style\_null_propagation

|||
|-|-|
| **Název pravidla** | dotnet_style_null_propagation |
| **ID pravidla** | IDE0031 |
| **Příslušné jazyky** | C#6.0 + a Visual Basic 14 + |
| **Hodnoty** | `true`– Raději použijte operátor s hodnotou null, pokud je to možné<br /><br />`false`– Raději použijte kontrolu Ternární hodnoty null, pokud je to možné |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

## <a name="net-code-quality-settings"></a>Nastavení kvality kódu .NET

Pravidla kvality v této části se vztahují na kód C# i Visual Basic. Slouží ke konfiguraci analyzátorů kódu, které jsou integrovány do integrovaného vývojového prostředí (IDE) sady Visual Studio. Informace o konfiguraci analyzátorů FxCop pomocí souboru EditorConfig najdete v tématu [Konfigurace analyzátorů FxCop](../code-quality/configure-fxcop-analyzers.md).

- [Předvolby parametrů](#parameter-preferences)
  - \_nepoužívané\_parametrykvality\_kódudotnet\_

### <a name="parameter-preferences"></a>Předvolby parametrů

Pravidla kvality v této části se týkají parametrů metod.

Tato pravidla by se mohla objevit v souboru *. editorconfig* následujícím způsobem:

```ini
# CSharp and Visual Basic code quality settings:
[*.{cs,vb}]
dotnet_code_quality_unused_parameters = all:suggestion
```

#### <a name="dotnet_code_quality_unused_parameters"></a>\_nepoužívané\_parametrykvality\_kódudotnet\_

|||
|-|-|
| **Název pravidla** | dotnet_code_quality_unused_parameters |
| **ID pravidla** | IDE0060 |
| **Příslušné jazyky** | C# a Visual Basic |
| **Hodnoty** | `all`-Flag metody s jakýmkoli přístupným příznakem, který obsahuje nepoužívané parametry<br /><br />`non_public`– Označí jenom neveřejné metody, které obsahují nepoužité parametry. |
| **Výchozí nastavení sady Visual Studio** | `all:suggestion` |

Příklady kódu:

```csharp
// dotnet_code_quality_unused_parameters = all:suggestion
public int GetNum() { return 1; }

// dotnet_code_quality_unused_parameters = non_public:suggestion
public int GetNum(int arg1) { return 1; }
```

```vb
' dotnet_code_quality_unused_parameters = all:suggestion
Public Function GetNum()
    Return 1
End Function

' dotnet_code_quality_unused_parameters = non_public:suggestion
Public Function GetNum(arg1 As Integer)
    Return 1
End Function
```

## <a name="c-code-style-settings"></a>C#nastavení stylu kódu

Pravidla stylu v této části platí pouze pro C# .

- [Implicitní a explicitní typy](#implicit-and-explicit-types)
  - var\_style\_CSharppro\_sestavené\_in_types\_
  - csharp\_style\_var\_when\_type\_is_apparent
  - csharp\_style\_var_elsewhere
- [Členové tvoření výrazy](#expression-bodied-members)
  - CSharp\_stylu\_výrazubodied_methods\_
  - csharp\_style\_expression\_bodied_constructors
  - csharp\_style\_expression\_bodied_operators
  - csharp\_style\_expression\_bodied_properties
  - csharp\_style\_expression\_bodied_indexers
  - csharp\_style\_expression\_bodied_accessors
  - CSharp\_stylu\_výrazubodied_lambdas\_
  - CSharp\_styl\_výrazutěle\_local_functions\_
- [Porovnávání vzorů](#pattern-matching)
  - CSharp\_porovnávání\_vzorů\_ve styluje\_scast_check\_\_\_
  - CSharp\_porovnávání\_vzorů\_stylůjako\_snull_check\_\_\_
- [Vložené deklarace proměnných](#inlined-variable-declarations)
  - CSharp\_–\_styl na řádku\_variable_declaration
- [Předvolby na úrovni výrazu](#c-expression-level-preferences)
  - csharp\_prefer\_simple\_default_expression
- [Předvolby kontroly "null"](#c-null-checking-preferences)
  - csharp\_style\_throw_expression
  - csharp\_style\_conditional\_delegate_call
- [Předvolby bloku kódu](#code-block-preferences)
  - csharp\_prefer_braces
- [Předvolby nepoužité hodnoty](#unused-value-preferences)
  - CSharp\_\_\_stylnepoužitého\_výrazu hodnoty statement_preference\_
  - styl\_\_CSharp nepoužitáhodnota\_assignment_preference\_
- [Předvolby indexu a rozsahu](#index-and-range-preferences)
  - styl\_CSharp\_preferovatindex_operator\_
  - styl\_CSharp\_preferovatrange_operator\_
- [Různé předvolby](#miscellaneous-preferences)
  - CSharp\_–\_Dekonstruovaný\_styl variable_declaration
  - CSharp\_vzor\_stylumístní\_nadanonymous_function\_\_
  - CSharp\_používající\_umístěnídirektiv\_
  - CSharp\_preferovat\_staticlocal_function\_
  - CSharp\_preferovat\_jednoduchéusing_statement\_
  - styl\_CSharp\_preferovatswitch_expression\_

### <a name="implicit-and-explicit-types"></a>Implicitní a explicitní typy

Pravidla stylu v této části se týkají použití klíčového slova [var](/dotnet/csharp/language-reference/keywords/var) a explicitního typu v deklaraci proměnné. Toto pravidlo lze použít samostatně pro předdefinované typy, pokud je typ zřejmý a jinde.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="csharp_style_var_for_built_in_types"></a>var\_style\_CSharppro\_sestavené\_in_types\_

|||
|-|-|
| **Název pravidla** | csharp_style_var_for_built_in_types |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Příslušné jazyky** | C#  |
| **Hodnoty** | `true`-Preferovat `var` se používá k deklaraci proměnných s integrovanými systémovými typy, jako je například`int`<br /><br />`false`-Preferovat explicitní typ `var` pro deklaraci proměnných s integrovanými systémovými typy, jako například`int` |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

#### <a name="csharp_style_var_when_type_is_apparent"></a>csharp\_style\_var\_when\_type\_is_apparent

|||
|-|-|
| **Název pravidla** | csharp_style_var_when_type_is_apparent |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Příslušné jazyky** | C#  |
| **Hodnoty** | `true`– Preferovat `var` , když je typ již uveden na pravé straně výrazu deklarace<br /><br />`false`-Preferovat explicitní typ `var` , pokud je již tento typ uveden na pravé straně výrazu deklarace |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

#### <a name="csharp_style_var_elsewhere"></a>csharp\_style\_var_elsewhere

|||
|-|-|
| **Název pravidla** | csharp_style_var_elsewhere |
| **ID pravidla** | IDE0007 a IDE0008 |
| **Příslušné jazyky** | C#  |
| **Hodnoty** | `true`-Preferovat `var` přes explicitní typ ve všech případech, pokud není přepsán jiným pravidlem stylu kódu.<br /><br />`false`-Preferovat explicitní typ `var` ve všech případech, pokud není přepsán jiným pravidlem stylu kódu |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

### <a name="expression-bodied-members"></a>Členové tvoření výrazy

Pravidla stylu v této části se týkají použití [členů Expression-těle](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members) , když se logika skládá z jediného výrazu. Toto pravidlo lze použít pro metody, konstruktory, operátory, vlastnosti, indexery a přistupující objekty.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
csharp_style_expression_bodied_lambdas = true:silent
csharp_style_expression_bodied_local_functions = false:silent
```

#### <a name="csharp_style_expression_bodied_methods"></a>CSharp\_stylu\_výrazubodied_methods\_

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_methods |
| **ID pravidla** | IDE0022 |
| **Příslušné jazyky** | C#6.0 +  |
| **Hodnoty** | `true`-Preferovat texty výrazu pro metody<br /><br />`when_on_single_line`– Preferovat texty výrazu pro metody, když budou představovat jeden řádek<br /><br />`false`-Preferovat blokové texty pro metody |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

#### <a name="csharp_style_expression_bodied_constructors"></a>csharp\_style\_expression\_bodied_constructors

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_constructors |
| **ID pravidla** | IDE0021 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro konstruktory<br /><br />`when_on_single_line`– Preferovat texty výrazu pro konstruktory, když budou představovat jeden řádek<br /><br />`false`-Preferovat blokové texty pro konstruktory |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

#### <a name="csharp_style_expression_bodied_operators"></a>csharp\_style\_expression\_bodied_operators

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_operators |
| **ID pravidla** | IDE0023 a IDE0024 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro operátory<br /><br />`when_on_single_line`– Preferovat texty výrazu pro operátory, když budou být jedním řádkem<br /><br />`false`-Preferovat blokové texty pro operátory |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

#### <a name="csharp_style_expression_bodied_properties"></a>csharp\_style\_expression\_bodied_properties

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_properties |
| **ID pravidla** | IDE0025 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro vlastnosti<br /><br />`when_on_single_line`– Preferovat tělo výrazu pro vlastnosti, když budou představovat jeden řádek<br /><br />`false`-Preferovat blokové texty pro vlastnosti |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

#### <a name="csharp_style_expression_bodied_indexers"></a>csharp\_style\_expression\_bodied_indexers

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_indexers |
| **ID pravidla** | IDE0026 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro indexery<br /><br />`when_on_single_line`– Preferovat texty výrazu pro indexery, když budou být jedním řádkem<br /><br />`false`-Preferovat blokové texty pro indexery |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _values[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

#### <a name="csharp_style_expression_bodied_accessors"></a>csharp\_style\_expression\_bodied_accessors

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_accessors |
| **ID pravidla** | IDE0027 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro přistupující objekty<br /><br />`when_on_single_line`– Preferovat texty výrazu pro přistupující objekty, když budou být jedním řádkem<br /><br />`false`-Preferovat blokové texty pro přistupující objekty |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

#### <a name="csharp_style_expression_bodied_lambdas"></a>CSharp\_stylu\_výrazubodied_lambdas\_

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_lambdas |
| **ID pravidla** | IDE0053 |
| **Hodnoty** | `true`-Preferovat texty výrazu pro výrazy lambda<br /><br />`when_on_single_line`– Preferovat výrazy výrazů pro lambda, pokud budou být jedním řádkem<br /><br />`false`-Preferovat blokové texty pro výrazy lambda |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_lambdas = true
Func<int, int> square = x => x * x;

// csharp_style_expression_bodied_lambdas = false
Func<int, int> square = x => { return x * x; };
```

#### <a name="csharp_style_expression_bodied_local_functions"></a>CSharp\_styl\_výrazutěle\_local_functions\_

Počínaje C# 7,0 C# podporuje [místní funkce](/dotnet/csharp/programming-guide/classes-and-structs/local-functions). Lokální funkce jsou soukromé metody typu, které jsou vnořené v jiném členu.

|||
|-|-|
| **Název pravidla** | csharp_style_expression_bodied_local_functions |
| **ID pravidla** | IDE0061 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat texty výrazu pro místní funkce<br /><br />`when_on_single_line`– Preferovat tělo výrazu pro místní funkce, když budou to jeden řádek<br /><br />`false`-Preferovat blokové texty pro místní funkce |
| **Výchozí nastavení sady Visual Studio** | `false:silent` |

Příklady kódu:

```csharp
// csharp_style_expression_bodied_local_functions = true
void M()
{
    Hello();
    void Hello() => Console.WriteLine("Hello");
}

// csharp_style_expression_bodied_local_functions = false
void M()
{
    Hello();
    void Hello()
    {
        Console.WriteLine("Hello");
    }
}
```

### <a name="pattern-matching"></a>Porovnávání vzorů

Pravidla stylu v této části se týkají použití porovnávání se [vzorci](/dotnet/csharp/pattern-matching) v C#.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="csharp_style_pattern_matching_over_is_with_cast_check"></a>CSharp\_porovnávání\_vzorů\_ve styluje\_scast_check\_\_\_

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_matching_over_is_with_cast_check |
| **ID pravidla** | IDE0020 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat porovnávání vzorů místo `is` výrazů s přetypováními typů<br /><br />`false`-Preferovat `is` výrazy s přetypováními typu místo porovnávání vzorů |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

#### <a name="csharp_style_pattern_matching_over_as_with_null_check"></a>CSharp\_porovnávání\_vzorů\_stylůjako\_snull_check\_\_\_

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_matching_over_as_with_null_check |
| **ID pravidla** | IDE0019 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat porovnávání vzorů místo `as` výrazů s kontrolou null k určení, jestli je něco konkrétního typu<br /><br />`false`-Preferovat `as` výrazy s nulovými kontrolami namísto porovnávání vzorů, abyste zjistili, jestli je něco konkrétního typu |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

### <a name="inlined-variable-declarations"></a>Vložené deklarace proměnných

Toto pravidlo stylu se týká `out` , zda jsou proměnné deklarovány jako vložené nebo nikoli. Počínaje C# 7 můžete [deklarovat proměnnou out v seznamu argumentů volání metody](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument), nikoli v deklaraci samostatné proměnné.

#### <a name="csharp_style_inlined_variable_declaration"></a>CSharp\_–\_styl na řádku\_variable_declaration

|||
|-|-|
| **Název pravidla** | csharp_style_inlined_variable_declaration |
| **ID pravidla** | IDE0018 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat `out` proměnné, které se mají deklarovat jako vložené v seznamu argumentů volání metody, pokud je to možné<br /><br />`false`-Preferovat `out` proměnné, které se mají deklarovat před voláním metody |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

### <a name="c-expression-level-preferences"></a>C#Předvolby na úrovni výrazu

Pravidla stylu v této části se týkají předvoleb na úrovni výrazu.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
```

#### <a name="csharp_prefer_simple_default_expression"></a>csharp\_prefer\_simple\_default_expression

Toto pravidlo stylu se týká použití [ `default` literálu pro výrazy výchozích hodnot](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) , když kompilátor může odvodit typ výrazu.

|||
|-|-|
| **Název pravidla** | csharp_prefer_simple_default_expression |
| **ID pravidla** | IDE0034 |
| **Příslušné jazyky** | C#7.1 +  |
| **Hodnoty** | `true`– Preferovat `default``default(T)`<br /><br />`false`– Preferovat `default(T)``default` |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

### <a name="c-null-checking-preferences"></a>C#předvolby pro kontrolu hodnoty null

Tato pravidla stylu se týkají syntaxe kolem `null` kontroly, včetně použití `throw` výrazů nebo `throw` příkazů a zda má být provedena kontrola s hodnotou null nebo použití operátoru podmíněného`?.`slučování () při volání [metody. výraz lambda](/dotnet/csharp/lambda-expressions)

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="csharp_style_throw_expression"></a>csharp\_style\_throw_expression

|||
|-|-|
| **Název pravidla** | csharp_style_throw_expression |
| **ID pravidla** | IDE0016 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`– Raději `throw` `throw` místo příkazů použít výrazy<br /><br />`false`– Raději `throw` `throw` místo výrazů použít příkazy |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

#### <a name="csharp_style_conditional_delegate_call"></a>csharp\_style\_conditional\_delegate_call

|||
|-|-|
| **Název pravidla** | csharp_style_conditional_delegate_call |
| **ID pravidla** | IDE0041 |
| **Příslušné jazyky** | C#6.0 +  |
| **Hodnoty** | `true`– Při volání výrazu lambda namísto kontroly hodnoty null`?.`se používá operátor podmíněného slučování ().<br /><br />`false`– Před voláním výrazu lambda se doporučuje provést kontrolu null, místo použití operátoru podmíněného slučování (`?.`). |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

### <a name="code-block-preferences"></a>Předvolby bloku kódu

Toto pravidlo stylu se týká použití složených závorek `{ }` k obklopení bloků kódu.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:silent
```

#### <a name="csharp_prefer_braces"></a>CSharp\_preferovat\_složené závorky

|||
|-|-|
| **Název pravidla** | csharp_prefer_braces |
| **ID pravidla** | IDE0011 |
| **Příslušné jazyky** | C# |
| **Hodnoty** | `true`-Preferovat složené závorky i pro jeden řádek kódu<br /><br />`false`-Preferovat žádné složené závorky, pokud je povoleno |
| **Výchozí nastavení sady Visual Studio** | `true:silent` |

Příklady kódu:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

### <a name="unused-value-preferences"></a>Předvolby nepoužité hodnoty

Tato pravidla stylu se týkají nepoužitých výrazů a přiřazení hodnot.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_unused_value_expression_statement_preference = discard_variable:silent
csharp_style_unused_value_assignment_preference = discard_variable:suggestion
```

#### <a name="csharp_style_unused_value_expression_statement_preference"></a>csharp_style_unused_value_expression_statement_preference

|||
|-|-|
| **Název pravidla** | csharp_style_unused_value_expression_statement_preference |
| **ID pravidla** | IDE0058 |
| **Příslušné jazyky** | C# |
| **Hodnoty** | `discard_variable`– Raději přiřaďte nepoužitý výraz k [](/dotnet/csharp/discards) zahození <br /><br />`unused_local_variable`– Raději přiřaďte nepoužitý výraz místní proměnné. |
| **Výchozí nastavení sady Visual Studio** | `discard_variable:silent` |

Příklady kódu:

```csharp
// Original code:
System.Convert.ToInt32("35");

// After code fix for IDE0058:

// csharp_style_unused_value_expression_statement_preference = discard_variable
_ = System.Convert.ToInt32("35");

// csharp_style_unused_value_expression_statement_preference = unused_local_variable
var unused = Convert.ToInt32("35");
```

#### <a name="csharp_style_unused_value_assignment_preference"></a>csharp_style_unused_value_assignment_preference

|||
|-|-|
| **Název pravidla** | csharp_style_unused_value_assignment_preference |
| **ID pravidla** | IDE0059 |
| **Příslušné jazyky** | C# |
| **Hodnoty** | `discard_variable`– Upřednostňuje použití zahození při přiřazení hodnoty, která se nepoužívá. [](/dotnet/csharp/discards)<br /><br />`unused_local_variable`– Raději použijte místní proměnnou při přiřazení hodnoty, která se nepoužívá. |
| **Výchozí nastavení sady Visual Studio** | `discard_variable:suggestion` |

Příklady kódu:

```csharp
// csharp_style_unused_value_assignment_preference = discard_variable
int GetCount(Dictionary<string, int> wordCount, string searchWord)
{
    _ = wordCount.TryGetValue(searchWord, out var count);
    return count;
}

// csharp_style_unused_value_assignment_preference = unused_local_variable
int GetCount(Dictionary<string, int> wordCount, string searchWord)
{
    var unused = wordCount.TryGetValue(searchWord, out var count);
    return count;
}
```

### <a name="index-and-range-preferences"></a>Předvolby indexu a rozsahu

Tato pravidla stylu se týkají použití operátorů index a rozsah, které jsou k dispozici v C# 8,0 a novějších verzích.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_prefer_index_operator = true:suggestion
csharp_style_prefer_range_operator = true:suggestion
```

#### <a name="csharp_style_prefer_index_operator"></a>styl\_CSharp\_preferovatindex_operator\_

|||
|-|-|
| **Název pravidla** | csharp_style_prefer_index_operator |
| **ID pravidla** | IDE0056 |
| **Příslušné jazyky** | C#8.0 + |
| **Hodnoty** | `true`– Raději použít `^` operátor při výpočtu indexu z konce kolekce<br /><br />`false`– Nedoporučuje se použít `^` operátor při výpočtu indexu z konce kolekce. |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_prefer_index_operator = true
string[] names = { "Archimedes", "Pythagoras", "Euclid" };
var index = names[^1];

// csharp_style_prefer_index_operator = false
string[] names = { "Archimedes", "Pythagoras", "Euclid" };
var index = names[names.Length - 1];
```

#### <a name="csharp_style_prefer_range_operator"></a>styl\_CSharp\_preferovatrange_operator\_

|||
|-|-|
| **Název pravidla** | csharp_style_prefer_range_operator |
| **ID pravidla** | IDE0057 |
| **Příslušné jazyky** | C#8.0 + |
| **Hodnoty** | `true`– Raději použít operátor `..` rozsahu při extrakci "řezu" kolekce<br /><br />`false`– Při extrakci řezu kolekce nedoporučuje `..` používat operátor rozsahu |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_prefer_range_operator = true
string sentence = "the quick brown fox";
var sub = sentence[0..^4];

// csharp_style_prefer_range_operator = false
string sentence = "the quick brown fox";
var sub = sentence.Substring(0, sentence.Length - 4);
```

### <a name="miscellaneous-preferences"></a>Různé předvolby

Tato část obsahuje různá pravidla stylu.

Příklad souboru *. editorconfig* :

```ini
# CSharp code style settings:
[*.cs]
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
csharp_using_directive_placement = outside_namespace:silent
csharp_prefer_static_local_function = true:suggestion
csharp_prefer_simple_using_statement = true:suggestion
csharp_style_prefer_switch_expression = true:suggestion
```

#### <a name="csharp_style_deconstructed_variable_declaration"></a>CSharp\_–\_Dekonstruovaný\_styl variable_declaration

|||
|-|-|
| **Název pravidla** | csharp_style_deconstructed_variable_declaration |
| **ID pravidla** | IDE0042 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`-Preferovat deklaraci dekonstruovaných proměnných<br /><br />`false`– Nepreferovat dekonstrukci v deklaracích proměnných |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

#### <a name="csharp_style_pattern_local_over_anonymous_function"></a>CSharp\_vzor\_stylumístní\_nadanonymous_function\_\_

Počínaje C# 7,0 C# podporuje [místní funkce](/dotnet/csharp/programming-guide/classes-and-structs/local-functions). Lokální funkce jsou soukromé metody typu, které jsou vnořené v jiném členu.

|||
|-|-|
| **Název pravidla** | csharp_style_pattern_local_over_anonymous_function |
| **ID pravidla** | IDE0039 |
| **Příslušné jazyky** | C#7.0 + |
| **Hodnoty** | `true`– Upřednostnit místní funkce přes anonymní funkce<br /><br />`false`– Upřednostnit anonymní funkce nad místními funkcemi |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

#### <a name="csharp_using_directive_placement"></a>CSharp\_pomocí\_directive_placement

|||
|-|-|
| **Název pravidla** | csharp_using_directive_placement |
| **ID pravidla** | IDE0065 |
| **Příslušné jazyky** | C# |
| **Hodnoty** | `outside_namespace`-Preferovat `using` direktivy, které mají být umístěny mimo obor názvů<br /><br />`inside_namespace`-Preferovat `using` direktivy, které mají být umístěny uvnitř oboru názvů |
| **Výchozí nastavení sady Visual Studio** | `outside_namespace:silent` |

Příklady kódu:

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{
    ...
}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
    ...
}
```

#### <a name="csharp_prefer_static_local_function"></a>CSharp\_preferovat\_staticlocal_function\_

|||
|-|-|
| **Název pravidla** | csharp_prefer_static_local_function |
| **ID pravidla** | IDE0062 |
| **Příslušné jazyky** | C#8.0 + |
| **Hodnoty** | `true`-Upřednostnit místní funkce, které mají být označeny`static`<br /><br />`false`-Nepreferovat místní funkce, které mají být označeny`static` |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_prefer_static_local_function = true
void M()
{
    Hello();
    static void Hello()
    {
        Console.WriteLine("Hello");
    }
}

// csharp_prefer_static_local_function = false
void M()
{
    Hello();
    void Hello()
    {
        Console.WriteLine("Hello");
    }
}
```

#### <a name="csharp_prefer_simple_using_statement"></a>CSharp\_preferovat\_jednoduchéusing_statement\_

|||
|-|-|
| **Název pravidla** | csharp_prefer_simple_using_statement |
| **ID pravidla** | IDE0063 |
| **Příslušné jazyky** | C#8.0 + |
| **Hodnoty** | `true`– Preferovat použití jednoduchého `using` příkazu<br /><br />`false`– Nedoporučujeme používat *jednoduchý* `using` příkaz. |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |

Příklady kódu:

```csharp
// csharp_prefer_simple_using_statement = true
using var a = b;

// csharp_prefer_simple_using_statement = false
using (var a = b) { }
```

#### <a name="csharp_style_prefer_switch_expression"></a>styl\_CSharp\_preferovatswitch_expression\_

|||
|-|-|
| **Název pravidla** | csharp_style_prefer_switch_expression |
| **ID pravidla** | IDE0066 |
| **Příslušné jazyky** | C#8.0 + |
| **Hodnoty** | `true`– Raději použijte `switch` výraz (představený s C# 8,0)<br /><br />`false`– Preferovat použití [příkazu switch](/dotnet/csharp/language-reference/keywords/switch) |
| **Výchozí nastavení sady Visual Studio** | `true:suggestion` |
| **Představená verze** | Visual Studio 2019 verze 16,2 |

Příklady kódu:

```csharp
// csharp_style_prefer_switch_expression = true
return x switch
{
    1 => 1 * 1,
    2 => 2 * 2,
    _ => 0,
};

// csharp_style_prefer_switch_expression = false
switch (x)
{
    case 1:
        return 1 * 1;
    case 2:
        return 2 * 2;
    default:
        return 0;
}
```

## <a name="see-also"></a>Viz také:

- [Konvence formátování](editorconfig-formatting-conventions.md)
- [Zásady vytváření názvů](editorconfig-naming-conventions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](editorconfig-code-style-settings-reference.md)
