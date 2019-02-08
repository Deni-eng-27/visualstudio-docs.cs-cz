---
title: 'Postupy: Rozdělení třídy na částečné třídy (návrhář tříd)'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Class Designer, partial classes
- partial classes, Class Designer
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 32ac7dc37787a91504988fc43636d49d2b3c9ce0
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55924029"
---
# <a name="how-to-split-a-class-into-partial-classes-in-class-designer"></a>Postupy: Rozdělení třídy na částečné třídy v Návrháři tříd

Můžete použít `partial` – klíčové slovo (`Partial` v jazyce Visual Basic) a rozdělit deklaraci třídy nebo struktury mezi několik deklarací. Můžete použít libovolný počet částečné deklarace.

Deklarace může být v jednom nebo více zdrojových souborů. Všechny deklarace musí být ve stejném sestavení a stejný obor názvů.

Částečné třídy jsou užitečné v několika situacích. Na velkých projektech třeba oddělení třídu do více souborů umožňuje více než jeden programátora pro práci na projektu ve stejnou dobu. Při práci s kódem, který generuje sada Visual Studio, můžete změnit třídu bez nutnosti znovu vytvářet zdrojový soubor. (Příklady kódu, který generuje sada Visual Studio zahrnují Windows Forms a webového kódu obálky služby). Můžete tedy vytvořit kód, který používá automaticky generovaný třídy, aniž byste museli upravovat soubor, který sada Visual Studio vytvoří.

Existují dva druhy částečné metody. V jazyce C# jsou volány deklarace a implementaci; v jazyce Visual Basic se nazývají deklaraci a implementaci.

**Návrhář tříd** podporuje částečné třídy a metody. Tvar typu v diagramu tříd, odkazuje na umístění jediné deklaraci částečné třídy. Pokud je částečná třída definovaná ve více souborech, můžete zadat umístění které deklarace **návrhář tříd** používat tak, že nastavíte **umístění nového člena** vlastnost v **vlastnosti**  okna. To znamená, když dvakrát kliknete na obrazec třídy **návrhář tříd** přejde do zdrojového souboru, který obsahuje deklaraci třídy, který je identifikován **umístění nového člena** vlastnost. Když dvakrát kliknete na částečné metody v obrazci třídy **návrhář tříd** přejde na deklaraci částečné metody. Také v **vlastnosti** okně **název_souboru** vlastnost odkazuje na umístění prohlášení. Pro částečné třídy **název_souboru** uvádí všechny soubory, které obsahují deklarace a implementaci kód pro danou třídu. Ale pro částečné metody **název_souboru** obsahuje pouze soubor, který obsahuje deklaraci částečné metody.

Následující příklady rozdělení definice třídy `Employee` do dvě deklarace, z nichž každý definuje jiný postup. Dvě Částečná definice v příkladech může být v jednom zdrojovém souboru nebo ve dvou různých zdrojových souborů.

> [!NOTE]
> Visual Basic používá definicí částečné třídy pro oddělení sady Visual Studio – kód generovaný z uživatelem definovaných kódu. Kód je rozdělené na samostatné zdrojové soubory. Například **Návrhář formulářů Windows** definuje částečné třídy pro ovládací prvky, jako `Form`. Generovaný kód v těchto ovládacích prvků byste neměli měnit.

Další informace o částečné typy v jazyce Visual Basic najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial).

## <a name="example"></a>Příklad

Pro rozdělení definice třídy, použijte `partial` – klíčové slovo (`Partial` v jazyce Visual Basic), jak je znázorněno v následujícím příkladu:

```csharp
// First part of class definition.
public partial class Employee
{
    public void CalculateWorkHours()
    {
    }
}

// Second part of class definition.
public partial class Employee
{
    public void CalculateTaxes()
    {
    }
}
```

```vb
' First part of class definition.
Partial Public Class Employee
    Public Sub CalculateWorkHours()
    End Sub
End Class

' Second part of class definition.
Partial Public Class Employee
    Public Sub CalculateTaxes()
    End Sub
End Class
```

## <a name="see-also"></a>Viz také:

- [Částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)
- [partial (typ) (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/partial-type)
- [partial (metoda) (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/partial-method)
- [Partial (Visual Basic)](/dotnet/visual-basic/language-reference/modifiers/partial)