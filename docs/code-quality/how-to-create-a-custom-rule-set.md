---
title: Vytvoření sady pravidel analýzy vlastního kódu
ms.date: 11/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 087651271de696345ed2bed97e24acf280af1cd6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025976"
---
# <a name="customize-a-rule-set"></a>Přizpůsobení sady pravidel

Můžete vytvořit vlastní sadu pravidel, která podle potřeb konkrétního projektu pro analýzu kódu.

## <a name="create-a-custom-rule-set"></a>Vytvoření vlastní sady pravidel

Chcete-li vytvořit vlastní pravidlo nastavte, můžete otevřít sadu předdefinovaných pravidel **s editorem sad pravidel**. Odtud můžete přidat nebo odebrat konkrétní pravidla a akce, která nastane, pokud došlo k porušení pravidla můžete změnit&mdash;například zobrazit upozornění nebo chybu.

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a pak vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýzy kódu** kartu.

3. V **spustit tuto sadu pravidel** rozevíracího seznamu, proveďte jednu z následujících akcí:

   - Vyberte sadu pravidel, který chcete přizpůsobit.

     \- nebo –

   - Vyberte  **\<Procházet... >** zadat sadu existujících pravidel, která se nenachází v seznamu.

4. Vyberte **otevřít** zobrazíte pravidla v editoru sad pravidel.

Můžete také vytvořit nový soubor sady pravidel z **nový soubor** dialogové okno:

1. Vyberte **souboru** > **nový** > **souboru**, nebo stiskněte klávesu **Ctrl**+**N**.

2. V **nový soubor** dialogové okno, vyberte **Obecné** kategorii na levé straně a pak vyberte **sady pravidel analýzy kódu**.

3. Vyberte **Open** (Otevřít).

   Nové *.ruleset* soubor se otevře v editoru sad pravidel.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>Vytvoření vlastního pravidla nastavit z více sad pravidel

1. V Průzkumníku řešení klikněte pravým tlačítkem myši na projekt a pak vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýzy kódu** kartu.

3. Vyberte  **\<zvolit sady více pravidel... >** z **spustit tuto sadu pravidel**.

4. V **přidat nebo odebrat sady pravidel** dialogové okno, vyberte pravidlo sad, které chcete zahrnout do nové sady pravidel.

   ![Přidání nebo odebrání dialogové okno sady pravidel](media/add-remove-rule-sets.png)

5. Vyberte **uložit jako**, zadejte název *.ruleset* souboru a pak vyberte **Uložit**.

   Nová sada pravidel je vybrán v **spustit tuto sadu pravidel** seznamu.

6. Vyberte **otevřete** otevřete novou sadu pravidel v editoru sad pravidel.

### <a name="rule-precedence"></a>Priorita pravidla

- Pokud je uvedené dva stejné pravidlo nebo víckrát v pravidle nastavit s jinou závažností, kompilátor vygeneruje chybu. Příklad:

   ```xml
   <RuleSet Name="Rules for ClassLibrary21" Description="Code analysis rules for ClassLibrary21.csproj." ToolsVersion="15.0">
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Warning" />
       <Rule Id="CA1021" Action="Error" />
     </Rules>
   </RuleSet>
   ```

- Pokud je uvedené dva stejné pravidlo nebo vícekrát v pravidle nastavit s *stejné* závažnost, může zobrazit následující upozornění v **seznam chyb**:

   **CA0063: Nepovedlo se načíst soubor sady pravidel '\[vaše] .ruleset ' nebo jeden z jeho závislých pravidlo nastavit soubory. Soubor neodpovídá schématu sady pravidel.**

- Pokud sada pravidel obsahuje podřízeným pravidlem nastavení s použitím **zahrnout** značky i podřízené a nadřazené sady pravidel seznamu stejné pravidlo, ale s jinou závažností, pak závažnost v nadřazené sadě pravidel má přednost. Příklad:

   ```xml
   <!-- Parent rule set -->
   <?xml version="1.0" encoding="utf-8"?>
   <RuleSet Name="Rules for ClassLibrary21" Description="Code analysis rules for ClassLibrary21.csproj." ToolsVersion="15.0">
     <Include Path="classlibrary_child.ruleset" Action="Default" />
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Warning" /> <!-- Overrides CA1021 severity from child rule set -->
     </Rules>
   </RuleSet>

   <!-- Child rule set -->
   <?xml version="1.0" encoding="utf-8"?>
   <RuleSet Name="Rules from child" Description="Code analysis rules from child." ToolsVersion="15.0">
     <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
       <Rule Id="CA1021" Action="Error" />
     </Rules>
   </RuleSet>
   ```

## <a name="name-and-description"></a>Název a popis

Chcete-li změnit zobrazovaný název sady pravidel, která je otevřená v editoru, otevřete **vlastnosti** okna tak, že vyberete **zobrazení** > **okno vlastností** na řádku nabídek. Zadejte zobrazovaný název v **název** pole. Můžete také zadat popis sady pravidel.

## <a name="next-steps"></a>Další kroky

Teď, když máte sadu pravidel, dalším krokem je přizpůsobit pravidla přidávání nebo odstraňování pravidel nebo úpravou závažnost porušení pravidel.

> [!div class="nextstepaction"]
> [Úprava pravidel v editoru sad pravidel](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>Viz také:

- [Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)