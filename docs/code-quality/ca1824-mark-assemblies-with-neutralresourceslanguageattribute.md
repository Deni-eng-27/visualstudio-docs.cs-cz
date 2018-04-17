---
title: 'CA1824: Označte sestavení pomocí atributu NeutralResourcesLanguageAttribute | Microsoft Docs'
ms.date: 03/29/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3fdca585cf2c706dc83ecf9c1f7735c0d9d4f47e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Označte sestavení pomocí atributu NeutralResourcesLanguageAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Obsahuje sestavení **ResX**– na základě prostředků, ale nemá <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> použije na ni.

## <a name="rule-description"></a>Popis pravidla

<xref:System.Resources.NeutralResourcesLanguageAttribute> Atribut informuje správce prostředků aplikace výchozí jazykovou verzi. Pokud výchozí jazykovou verzi prostředky se vloží do hlavní sestavení aplikace, a <xref:System.Resources.ResourceManager> má získat prostředky, které patří do stejné jazykovou verzi jako výchozí jazykovou verzi <xref:System.Resources.ResourceManager> automaticky použije prostředků umístěných v hlavní sestavení Namísto hledání pro satelitní sestavení. To obchází testu obvyklým sestavení, zlepšuje výkon vyhledávání na první prostředek zatížení a může snížit pracovní sady.

> [!TIP]
> V tématu [balení a nasazení prostředků](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) pro proces, <xref:System.Resources.ResourceManager> používá k testu pro soubory prostředků.

## <a name="fix-violations"></a>Opravit porušení

Opravit porušení toto pravidlo, přidejte atribut do sestavení a zadat jazyk prostředků neutrální jazykové verze.

### <a name="to-specify-the-neutral-language-for-resources"></a>Chcete-li určit neutrální jazyk pro prostředky

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak vyberte **vlastnosti**.

2. Vyberte **aplikace** a pak vyberte **informací o sestavení**.

   > [!NOTE]
   > Pokud projektu je .NET standardní nebo .NET Core projekt, vyberte **balíček** kartě.

3. Vyberte jazyk z **neutrální jazyk** nebo **neutrální jazyk sestavení** rozevíracího seznamu.

4. Vyberte **OK**.

## <a name="when-to-suppress-warnings"></a>Při potlačení upozornění

Je přípustné upozornění toto pravidlo potlačit. Však může snížit výkon při spouštění.

## <a name="see-also"></a>Viz také

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [Prostředky v aplikacích klasické pracovní plochy (.NET)](/dotnet/framework/resources/)
- [CA1703 - řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701 - řetězec prostředku, který složených slov by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)