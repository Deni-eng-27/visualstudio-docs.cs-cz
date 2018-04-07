---
title: Vytvoření pravidel nástroje Analýza kódu vlastní nastavení v sadě Visual Studio | Microsoft Docs
ms.date: 04/04/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a094b6c59eb4e1d95949dc35a5c0479edb4d5a76
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="custom-rule-sets"></a>Vlastních sad pravidel

Můžete vytvořit vlastní *sadu pravidel* podle potřeb konkrétní projekt pro analýzu kódu.

## <a name="create-a-custom-rule-set"></a>Vytvoření vlastní sady pravidel

Chcete-li vytvořit vlastní pravidlo nastavte, můžete otevřít předdefinované pravidlo nastavené v **s editorem sad pravidel**. Odtud můžete přidat nebo odebrat konkrétní pravidla a můžete změnit akci, která nastane při porušení pravidlo&mdash;například zobrazit upozornění nebo chybu.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýza kódu** kartě.

3. V **spuštění této sady pravidel** rozevíracího seznamu, proveďte jednu z následujících akcí:

    - Vyberte sadu pravidel, který chcete přizpůsobit.

     \- nebo –

    - Vyberte  **\<Procházet... >** k určení nastavení existující pravidlo, které se nenachází v seznamu.

4. Vyberte **otevřete** zobrazíte pravidla v editoru sadu pravidel.

Můžete také vytvořit nový soubor sady pravidel z **nový soubor** dialogové okno:

1. Vyberte **soubor** > **nový** > **soubor**, nebo stiskněte klávesu **Ctrl**+**N**.

2. V **nový soubor** dialogové okno, vyberte **Obecné** kategorie na levé straně a potom vyberte **sady pravidel analýzy kódu**.

3. Vyberte **otevřete**.

   Nové *analýza* soubor se otevře v editoru sadu pravidel.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>Vytvoření vlastního pravidla nastavit z více sad pravidel

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a potom vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýza kódu** kartě.

3. Vyberte  **\<zvolte více pravidlo nastaví... >** z **spuštění této sady pravidel**.

4. V **přidat nebo odebrat pravidlo nastaví** dialogové okno, vyberte pravidlo sad, které chcete zahrnout do vaší nové sady pravidel.

   ![Přidat nebo odebrat dialogové okno sady pravidel](media/add-remove-rule-sets.png)

5. Vyberte **uložit jako**, zadejte název *analýza* souboru a potom vyberte **Uložit**.

   Nové sady pravidel je vybraný v **spuštění této sady pravidel** seznamu.

6. Vyberte **otevřete** otevřít nové pravidlo nastavené v editoru sadu pravidel.

## <a name="name-and-description"></a>Název a popis

Pokud chcete změnit zobrazovaný název sadu pravidel, která je otevřen v editoru, otevřete **vlastnosti** okno výběrem **zobrazení** > **vlastnosti – okno** v řádku nabídek. Zadejte zobrazovaný název v **název** pole. Můžete také zadat popis pro sadu pravidel.

## <a name="next-steps"></a>Další kroky

Teď, když máte sadu pravidel, dalším krokem je přidání nebo odebrání pravidla nebo úpravou závažnost porušení pravidel přizpůsobit pravidla.

> [!div class="nextstepaction"]
> [Změňte pravidla, v editoru sadu pravidel](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>Viz také

- [Postupy: Konfigurace Analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)