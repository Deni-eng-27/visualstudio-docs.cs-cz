---
title: 'CA1725: Názvy parametrů by měly odpovídat základní deklaraci | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 554282099426cc82acfd999b3f165573b7e21b5f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629303"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: Názvy parametrů by měly odpovídat základní deklaraci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1725: názvy parametrů by měly odpovídat základní deklaraci](https://docs.microsoft.com/visualstudio/code-quality/ca1725-parameter-names-should-match-base-declaration).  
  
TypeName | ParameterNamesShouldMatchBaseDeclaration |  
| ID kontroly | CA1725 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Název parametru v externě viditelné metodě přepsání neodpovídá názvu parametru v základní deklaraci metody nebo název parametru v deklaraci metody rozhraní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konzistentní pojmenování parametrů v hierarchii přetěžování zvyšuje použitelnost přetížení metody. Název parametru, který se v odvozené metodě liší od názvu v základní deklaraci, může způsobit zmatení, zda se u metody jedná o přepis základní metody, nebo o nové přetížení metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přejmenujte parametr odpovídat základní deklaraci. Oprava je zásadní změny pro metody viditelné modelu COM.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla s výjimkou metod viditelné modelu COM v knihovnách, které byly dříve součástí.



