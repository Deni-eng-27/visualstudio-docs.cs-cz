---
title: 'Postupy: Vytváření typů s povolenou hodnotou Null (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- nullable types, Class Designer
- Class Designer [Visual Studio], nullable types
ms.assetid: 84673a89-3f6d-4668-919e-1c0f56182fe5
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5ef167e83bc8f27a53405ef6ab7a3f9271863b4d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-create-a-nullable-type-in-class-designer"></a>Postupy: vytvoření typu s povolenou hodnotou Null v Návrháři tříd

Některé typy hodnot vždy nějaké (nebo potřebujete) definovanou hodnotu. Toto je běžnou praxí v databázích, kde některá pole nemusí být přiřazeny žádnou hodnotu. Například můžete do pole databáze do označují, že je ještě nebyly přiřazeny hodnotu přiřadit hodnotu null.

A *typ s možnou hodnotou Null* je typ hodnoty, které rozšířit tak, aby trvá typické rozsahu hodnot pro daný typ a také hodnotu null. Například s možnou hodnotou NULL z `Int32`, také jako s možnou hodnotou Null označují jako\<Int32 >, může být přiřazena libovolná hodnota od -2147483648 2147483647 nebo jej lze přiřadit hodnotu null. Nullable\<bool > je možné přiřadit hodnoty `True`, `False`, nebo hodnota null (žádná hodnota, na všech).

Typy s možnou hodnotou Null jsou instancemi třídy <xref:System.Nullable%601> struktura. Každá instance typu s povolenou hodnotou Null má dvě veřejné vlastnosti jen pro čtení `HasValue` a `Value`:

-   `HasValue` je typu `bool` a určuje, zda proměnná obsahuje hodnotu definované. `True` znamená, že proměnná obsahuje hodnotu než null. Pro hodnotu definovanou můžete otestovat pomocí příkazu `if (x.HasValue)` nebo `if (y != null)`.

-   `Value` je stejného typu jako nadřazený typ. Pokud `HasValue` je `True`, `Value` obsahuje hodnotu smysluplný. Pokud `HasValue` je `False`, přístupu k `Value` vyvolá výjimku neplatná operace.

Ve výchozím nastavení, když deklarovat proměnnou jako typ s možnou hodnotou Null, má žádné definované hodnoty (`HasValue` je `False`), jiné než výchozí hodnotu její základní typ hodnoty.

Návrhář tříd zobrazí typu s povolenou hodnotou Null, stejně jako se zobrazí jeho zdrojovým typem.

Další informace o typech s povolenou hodnotou Null v jazyce C#, najdete v části [typy s možnou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/index). Další informace o typech s povolenou hodnotou Null v jazyce Visual Basic najdete v tématu [typy s možnou hodnotou Null hodnot](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types).

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-a-nullable-type-by-using-the-class-designer"></a>Přidejte typ s možnou hodnotou Null pomocí návrháře tříd

1.  V diagramu tříd rozbalit existující třídy nebo vytvořte novou třídu.

2.  Přidat třídu do projektu, na **diagramu tříd** nabídky, klikněte na tlačítko **přidat** > **přidat třídu**.

3.  Na rozšíření třídy tvaru, **diagramu tříd** nabídky, klikněte na tlačítko **rozbalte**.

4.  Vyberte třídu tvaru. Na **diagramu tříd** nabídky, klikněte na tlačítko **přidat** > **pole**. Nové pole, která má výchozí název **pole** se zobrazí ve tvaru třídy a taky ve **podrobností třídy** okno.

5.  V **název** sloupec **podrobností třídy** okno (nebo ve třídě utvářejí sám sebe), změňte název nového pole na platný a smysluplný název.

6.  V **typ** sloupec **podrobností třídy** okně deklarovat typ jako typ s možnou hodnotou Null tak, že zadáte následující:

    - `int?` (Visual C#)
    - `Nullable(Of Integer)` (Visual Basic)

## <a name="to-add-a-nullable-type-by-using-the-code-editor"></a>Přidejte typ s možnou hodnotou Null pomocí editoru kódu

1.  Přidejte třídu do projektu. Vyberte uzel projektu v **Průzkumníku řešení**a na **projektu** nabídky, klikněte na tlačítko **přidat třídu**.

2.  V souboru cs nebo VB nové třídy přidejte jeden nebo více typů s povolenou hodnotou Null novou třídu do deklaraci třídy.

    ```csharp
    // Declare a nullable type in Visual C#:
    class Test
    {
       int? building_number = 5;
    }
    ```

    ```vb
    ' Declare a nullable type in Visual Basic:
    Class Test
       Dim buildingNumber As Nullable(Of Integer) = 5
    End Class
    ```

3.  Ze třídy zobrazení přetáhněte novou ikonu třídy na návrhovou plochu návrhář tříd. Třída obrazce se zobrazí v diagramu tříd.

4.  Rozbalte Podrobnosti obrazce Třída a přesuňte ukazatel myši nad členy třídy. Popisek zobrazí deklaraci každého člena.

5.  Klikněte pravým tlačítkem na tvar třídu a klikněte na tlačítko **podrobností třídy**. Můžete zobrazit nebo upravit vlastnosti nového typu v **podrobností třídy** okno.

## <a name="see-also"></a>Viz také

- <xref:System.Nullable%601>
- [Typy s povolenou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/index)
- [Použití typů s povolenou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types)
- [Postupy: Identifikace typu s povolenou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type)
- [Typy hodnot s povolenou hodnotou Null](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)
