---
title: T4 Výstup – direktiva | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 03a14993-47ad-4f2e-8032-57db28d5842a
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9262ec994ec847c38ec8d5c1ad95010a929cc4ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62549526"
---
# <a name="t4-output-directive"></a>T4 – direktiva Output
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] textových šablon, `output` – direktiva se používá k definování příponu názvu souboru a kódování transformovaný soubor.  
  
 Například pokud vaše [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projekt obsahuje soubor šablony s názvem **MyTemplate.tt** obsahující následující direktivy:  
  
 `<#@output extension=".cs"#>`  
  
 potom [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] vygeneruje soubor s názvem **MyTemplate.cs**  
  
 `output` Nevyžadoval – direktiva šablony textu za běhu (Předzpracované). Místo toho vaše aplikace získá vygenerovaný řetězec voláním `TextTransform()`. Další informace najdete v tématu [generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="using-the-output-directive"></a>Pomocí – direktiva Output  
  
```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 Měl by existovat více než jeden `output` direktiv v každé textové šabloně.  
  
## <a name="extension-attribute"></a>atribut rozšíření  
 Určuje příponu názvu souboru generovaný text výstupního souboru.  
  
 Výchozí hodnota je **.cs**  
  
 Příklady:  
 `<#@ output extension=".txt" #>`  
  
 `<#@ output extension=".htm" #>`  
  
 `<#@ output extension=".cs" #>`  
  
 `<#@ output extension=".vb" #>`  
  
 Přípustné hodnoty:  
 Žádné platnou příponu názvu souboru.  
  
## <a name="encoding-attribute"></a>kódování s atributem  
 Určuje kódování určené k použití při vygenerování výstupního souboru. Příklad:  
  
 `<#@ output encoding="utf-8"#>`  
  
 Výchozí hodnota je kódování používá soubor textové šablony.  
  
 Přípustné hodnoty:  
 `us-ascii`  
  
 `utf-16BE`  
  
 `utf-16`  
  
 `utf-8`  
  
 `utf-7`  
  
 `utf-32`  
  
 `0` (Výchozí systémové nastavení)  
  
 Obecně platí, můžete použít název_webového_serveru řetězec nebo číslo znakovou stránku, která u všech kódování vrácený <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>.
