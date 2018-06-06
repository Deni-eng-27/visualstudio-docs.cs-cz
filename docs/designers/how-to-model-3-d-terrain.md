---
title: 'Postupy: Model 3D geologické struktury'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b62ad2d954435e5556f2f427d531d806dfb7be18
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745575"
---
# <a name="how-to-model-3d-terrain"></a>Postupy: Model 3D geologické struktury

Tento článek ukazuje, jak použití editoru Model pro vytvoření modelu 3D geologické struktury.

## <a name="create-a-3d-terrain-model"></a>Vytvoření modelu 3D geologické struktury

3D geologické struktury můžete vytvořit tak, že roviny zajistit další řezy rozdělení sítě SAN a pak manipulace s jejich vrcholy vytvořit zajímavé funkce geologické struktury.

Jakmile budete hotovi, modelu by měl vypadat přibližně takto:

![3&#45;scény D, který znázorňuje model geologické struktury](../designers/media/digit-terrain-model.png)

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte 3D model pro práci s. Informace o tom, jak přidat model do projektu, najdete v části Začínáme v [modelu Editor](../designers/model-editor.md).

2.  Přidejte do roviny scény. V **sada nástrojů**v části **tvarů**, vyberte **roviny** a přesunout ho na plochu návrháře.

    > [!TIP]
    > Usnadnění roviny objekt pro práci s může být rámce v návrhové ploše. V **vyberte** režimu, vyberte objekt roviny a potom na panelu nástrojů editoru modelu, vyberte **rámce objekt** tlačítko.

3.  Zadejte režim vzhled výběru. Na panelu nástrojů editoru modelu zvolte **vyberte vzhled**.

4.  Rozdělit plochy. V režimu výběru řez zvolte roviny jednou aktivace pro výběr a potom zvolte jej znovu a vyberte jeho pouze vzhled. Na panelu nástrojů editoru modelu zvolte **Rozdělit vzhled**. Tento postup přidá novou vrcholy do roviny, která rozdělená do čtyř oddílů stejně velké.

5.  Vytvořte více dílčích dělení. S novou řezy stále vybrán, zvolte **Rozdělit vzhled** dvakrát. Tím se vytvoří celkem 64 řezy. Vytvořením více dílčích dělení můžete udělit geologické struktury více podrobností.

6.  Zadejte režim výběru bodu. Na panelu nástrojů editoru modelu zvolte **vyberte bod**.

7.  Změňte bod pro vytvoření funkce geologické struktury. V režimu výběru bod, vyberte jeden z bodů a potom na panelu nástrojů editoru modelu, vyberte **přeložit** nástroj. Pole, která představuje bod se zobrazí na návrhovou plochu. Použijte na zelenou šipku přesunout pole a tím změnit výška bodu. Opakujte tento krok pro různé body k vytvoření zajímavé funkce geologické struktury.

    > [!TIP]
    > Můžete vybrat několik bodů najednou o jejich úpravu jednotným způsobem.

Model geologické struktury je dokončena. Tady je poslední model znovu s Phong stínování použít:

![3&#45;scény D, který znázorňuje model geologické struktury](../designers/media/digit-terrain-model.png)

Tento model geologické struktury můžete použít k předvedení efektu barevného přechodu shaderu, která je popsána v [postupy: vytvoření přechodu shaderu na základě geometrie](../designers/how-to-create-a-geometry-based-gradient-shader.md).

## <a name="see-also"></a>Viz také:

- [Editor modelů](../designers/model-editor.md)