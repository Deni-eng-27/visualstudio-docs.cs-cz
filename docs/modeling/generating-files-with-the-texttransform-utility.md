---
title: Generování souborů pomocí nástroje TextTransform v sadě Visual Studio
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 065d9e23a8ae8b5e328786bb195d191df1388abb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="generate-files-with-the-texttransform-utility"></a>Generování souborů pomocí nástroje TextTransform

TextTransform.exe je nástroj příkazového řádku, který můžete použít k transformaci textové šablony. Při volání TextTransform.exe je zadat jako argument název textového souboru šablony. TextTransform.exe volá transformační modul text a zpracuje textové šablony. TextTransform.exe se obvykle nazývá z skriptů. Není však obvykle vyžaduje, protože je možné provádět transformací textu v sadě Visual Studio nebo v procesu sestavení.

> [!NOTE]
> Pokud chcete provést transformací textu v rámci procesu sestavení, zvažte použití úlohy transformace nástroje MSBuild text. Další informace najdete v tématu [generování kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md). Na počítači, na kterém [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalován, můžete je zapsat také aplikace nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, které můžete transformace textových šablon. Další informace najdete v tématu [zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md).

 TextTransform.exe se nachází v následujícím adresáři:

 **\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE**

pro edice Professional nebo

 **\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**

 pro Enterprise edition.

V předchozích verzích sady Visual Studio se soubor nachází v následujícím umístění:

**\Program Files (x86)\Common Files\Microsoft Shared\TextTemplating\{version}**

{version}, kde závisí na nainstalovanou předchozí verzi.

## <a name="syntax"></a>Syntaxe

```
TextTransform [<options>] <templateName>
```

### <a name="parameters"></a>Parametry

|**Argument**|**Popis**|
|------------------|---------------------|
|`templateName`|Určuje název souboru šablony, kterou chcete transformace.|

|**Možnost**|**Popis**|
|----------------|---------------------|
|**-out** \<název souboru >|Soubor, ke kterému je zapsán výstup transformace.|
|**-r** \<sestavení >|Sestavení použité pro kompilaci a spuštění textové šablony.|
|**-u** \<obor názvů >|Obor názvů, který se používá pro kompilaci šablony.|
|**-I** \<includedirectory >|Adresář, který obsahuje textové šablony obsažené v šabloně zadaný text.|
|**-P** \<referencepath >|Adresář pro vyhledávání pro sestavení zadané v rámci šablony text nebo pro použití **- r** možnost.<br /><br /> Například například sestavení, které používá pro Visual Studio API, použijte<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|
|**-dp** \<processorName >!\< Název třídy >! \<assemblyName&#124;codeBase >|Název, název typu úplné a sestavení direktivy procesoru, který slouží ke zpracování vlastní direktivy v textové šablony.|
|**-a** [processorName]! [directiveName]! \<parameterName >! \<parameterValue >|Zadejte hodnotu parametru direktivy procesoru. Pokud zadáte pouze název parametru a hodnota, bude k dispozici pro všechny procesory direktiv parametr. Pokud zadáte procesoru direktiv, parametr je k dispozici pouze určeným procesorem. Pokud zadáte název směrnice, parametr je k dispozici jenom v případě, že zadaný direktiva je zpracovávána.<br /><br /> Pro přístup k hodnotám parametrů z procesoru direktiv nebo textové šablony, použijte [ITextTemplatingEngineHost.ResolveParameterValue](https://msdn.microsoft.com/library/microsoft.visualstudio.texttemplating.itexttemplatingenginehost.resolveparametervalue.aspx). V textové šablony, zahrnují `hostspecific` v – direktiva šablony a vyvolání zprávy na `this.Host`. Příklad:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> Zadávejte vždy '!' označí, i v případě vynechání volitelné procesoru a direktivy názvy. Příklad:<br /><br /> `-a !!param!value`|
|**-h**|Poskytuje nápovědu.|

## <a name="related-topics"></a>Související témata

|Úloha|Téma|
|----------|-----------|
|Generování souborů v řešení systému [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|Zápis procesory direktiv k transformaci zdrojům dat.|[Přizpůsobení transformace textu T4](../modeling/customizing-t4-text-transformation.md)|
|Zápis textu ukázka hostitele, který umožňuje vyvolání textové šablony z vlastní aplikace.|[Zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md)|