---
title: Soubor vlastností, JavaScript | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- javascript.project.property.expandedsdknode.fileversion
- javascript.project.property.expandedsdknode.uri
- javascript.project.property.expandedsdknode.filename
- javascript.project.property.reference.description
- javascript.project.property.reference.specificversion
- javascript.project.property.reference.identity
- javascript.project.property.fullpath
- javascript.project.property.packageaction
- javascript.project.property.reference.package
- javascript.project.property.copytooutputdirectory
- javascript.project.property.expandedsdknode.sdkpath
- javascript.project.property.reference.filetype
- javascript.project.property.reference.culture
- javascript.project.property.filename
- javascript.project.property.reference.resolvedpath
- javascript.project.property.reference.version
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 00527cf13d978da5a10e7745049df63f24e7a15c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65688752"
---
# <a name="file-properties-javascript"></a>Vlastnosti souboru, JavaScript
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vlastnosti souboru můžete použít k označení jaké akce systém projektu by měl provádět na souborech. Můžete třeba nastavit vlastnosti souboru k označení, zda má soubor přidat do balíčku jako soubor prostředků.  
  
 Můžete vybrat libovolný soubor v Průzkumníku řešení a pak zkontrolujte její vlastnosti v okně Vlastnosti. Soubory jazyka JavaScript máte čtyři vlastnosti: **Kopírovat do výstupního adresáře**, **balíček akce**, **název souboru**, a **cesta k souboru**.  
  
## <a name="file-properties"></a>Vlastnosti souboru  
 Tato část popisuje vlastnosti, které jsou společné pro soubory jazyka JavaScript.  
  
### <a name="copy-to-output-directory-property"></a>Kopírovat do výstupního adresáře vlastnost  
 Tato vlastnost určuje podmínky, za kterých bude možné vybraný zdrojový soubor zkopírován do výstupního adresáře. Vyberte **nekopírovat** Pokud je soubor nikdy, které se mají zkopírovat do výstupního adresáře. Vyberte **vždy Kopírovat** je-li soubor vždy zkopírovány do výstupního adresáře. Vyberte **kopírovat, pokud je novější** Pokud je soubor, které se mají zkopírovat, pouze pokud je novější než stávající soubor se stejným názvem ve výstupním adresáři.  
  
### <a name="package-action"></a>Akce balíčku  
 **Akce balíčku** vlastnost indikuje, co Visual Studio dělá pomocí souboru při spuštění sestavení. **Balíček akce** může mít jednu z několika hodnot:  
  
- **Žádný** – soubor není zahrnutý v manifestu balíčku. Příkladem je textový soubor, který obsahuje dokumentaci, například soubor Readme.  
  
- **Obsahu** – soubor je zahrnutý v manifestu balíčku. Například toto nastavení je výchozí hodnota pro HTML, JS, CSS, obrázek, zvukový nebo video soubor.  
  
- **Manifest** – soubor není zahrnutý v manifestu balíčku. Místo toho soubor se používá pro vstup při generování manifestu balíčku. Toto je výchozí hodnota pro soubor package.appxmanifest.  
  
- **Prostředek** – soubor není zahrnutý v manifestu balíčku. Obsah souboru místo toho jsou indexovány v balíček prostředků indexu (PRI), která přejdou do manifestu balíčku. To se obvykle používá pro soubory prostředků.  
  
  Výchozí hodnota pro **akce balíčku** závisí na příponu souboru, který přidáte do řešení.  
  
### <a name="file-name-property"></a>Vlastnost název souboru  
 Zobrazuje název souboru jako hodnota určená pouze pro čtení. Pokud chcete přejmenovat soubor, klikněte pravým tlačítkem v Průzkumníku řešení a vyberte **přejmenovat**.  
  
### <a name="full-path-property"></a>Úplná cesta k vlastnosti  
 Zobrazí úplnou cestu k souboru jako hodnota určená pouze pro čtení. Chcete-li změnit cestu k souboru, můžete a přetahování souborů v Průzkumníku řešení.  
  
## <a name="reference-file-properties"></a>Vlastnosti odkazu na soubor  
 Tato část popisuje vlastnosti společné pro soubory, které odkazuje [!INCLUDE[win8_app_js](../../includes/win8-app-js-md.md)]. Když vyberete odkaz jako soubor .winmd, odkaz na sadu SDK, odkaz typu projekt projekt nebo odkaz na sestavení v Průzkumníku řešení, ostatní vlastnosti se může zobrazit v okně Vlastnosti podle typu souboru.  
  
### <a name="culture"></a>Jazyková verze  
 Zobrazí jazyk přidružený k odkazu.  
  
### <a name="file-type"></a>Typ souboru  
 Zobrazí typ souboru odkazu.  
  
### <a name="file-version"></a>Verze souboru  
 Zobrazí verzi souboru odkazu.  
  
### <a name="identity"></a>Identita  
 Zobrazí identitu, odkazu, který se používá v projektu, který je uložený v souboru projektu.  
  
### <a name="package"></a>Balíček  
 Zobrazí název manifestu balíčku přidruženého odkazu.  
  
### <a name="resolved-path"></a>Vyhodnocená cesta  
 Zobrazuje cestu k odkazu, který se používá v projektu.  
  
### <a name="sdk-path"></a>Cestu k sadě SDK  
 Zobrazuje cestu k odkazovanému souboru sady SDK.  
  
### <a name="uri"></a>Uri  
 Zobrazuje identifikátor URI, který musí být součástí projektu HTML nebo JavaScript soubory k zahrnutí souboru jako zdrojový soubor.  
  
### <a name="version"></a>Version  
 Zobrazí verze odkazu.  
  
## <a name="see-also"></a>Viz také  
 [NIB: Project Properties (Visual Studio)](https://msdn.microsoft.com/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)
