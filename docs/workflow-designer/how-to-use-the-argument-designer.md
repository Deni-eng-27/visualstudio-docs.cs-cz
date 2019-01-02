---
title: 'Návrhář postupu provádění – jak: Používání návrháře argumentů'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e73dcd167f6f267c7979f5c3ffb806b9f12d534a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891560"
---
# <a name="how-to-use-the-argument-designer"></a>Postupy: Používání návrháře argumentů

Porovnání s předchozími verzemi rozhraní .NET Framework, Návrhář argumentů umožňuje snadno povolit datový tok do a z aktivity. Návrhář přistupuje po kliknutí **argumenty** tlačítko v levém dolním rohu návrhové plátno. Návrhář obsahuje seznam argumentů, které se zobrazí ve formě tabulky a může být řada seřazena podle všech záhlaví sloupců, s výjimkou **výchozí hodnota** sloupce. Každý argument obsahuje název, v/out/v – out/vlastnost směr, typ a výchozí hodnota výrazu (pokud existuje). Název a hodnota výrazu výchozí nejsou upravitelné textové pole a typu a směru jsou rozevírací seznamy. Další informace najdete v tématu [proměnné a argumenty (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).

## <a name="to-create-a-new-argument"></a>Chcete-li vytvořit nový argument

1.  Otevřete řešení pracovního postupu nebo aktivity v sadě Visual Studio.

2.  Otevřít návrhář argumentů kliknutím **argumenty** tlačítko v levém dolním rohu návrhové plátno. Zobrazí se Návrhář argumentů.

3.  Klikněte na prázdný řádek označený **vytvořit Argument**. Tím se přidá nový řádek s argumentem nové pomocí následující výchozí hodnoty: argumentx pro **název** tam, kde x je celé číslo s počáteční hodnotou 1, které je automatický navýšeno vytvořit argument jedinečné názvy **v**  pro **směr**, a **řetězec** pro **typ argumentu**. Přidá se žádná hodnota pro **výchozí hodnota**. Tyto hodnoty můžete změnit kdykoli během procesu návrhu pracovního postupu.

    > [!NOTE]
    > Pokud chcete odstranit argument, argument kliknutím vyberte a stiskněte klávesu **odstranit** klíč.

## <a name="see-also"></a>Viz také:

- [Používání návrháře postupu provádění](developing-applications-with-the-workflow-designer.md)
- [Proměnné a argumenty](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)