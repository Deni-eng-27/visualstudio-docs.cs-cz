---
title: 'CA1824: Označte sestavení pomocí atributu NeutralResourcesLanguageAttribute | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8690a1f05f54fbac9427f4a03412e0a8054c51d2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779919"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Označte sestavení pomocí NeutralResourcesLanguageAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Obsahuje sestavení **ResX**– na základě zdrojů, ale nemá <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> použit.

## <a name="rule-description"></a>Popis pravidla
 **NeutralResourcesLanguage** informuje atribut **ResourceManager** jazyka, který byl použit k zobrazení prostředků neutrální jazykové verze pro sestavení. Když vyhledá prostředky ve stejnou jazykovou verzi jako jazyk neutrální prostředky **ResourceManager** automaticky používá prostředky, které jsou umístěné v hlavním sestavení. Dělá to namísto vyhledávání satelitního sestavení, který má aktuální jazykovou verzi uživatelského rozhraní pro aktuální vlákno. To zlepšuje výkon vyhledávání při prvním získání prostředků a může zmenšit vaši pracovní sadu.

## <a name="fixing-violations"></a>Oprava porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte atribut sestavení a určit jazyk prostředků neutrální jazykovou verzi.

## <a name="specifying-the-language"></a>Určení jazyka

#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>Pokud chcete určit jazyk prostředků neutrální jazykovou verzi

1.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti**.

2.  V levém navigačním panelu vyberte **aplikace**a potom klikněte na tlačítko **informace o sestavení**.

3.  V **informace o sestavení** dialogového okna, vyberte jazyk ze **neutrální jazyk** rozevíracího seznamu.

4.  Klikněte na **OK**.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je přípustné potlačit upozornění tohoto pravidla. Však může snížit výkon při spuštění.
