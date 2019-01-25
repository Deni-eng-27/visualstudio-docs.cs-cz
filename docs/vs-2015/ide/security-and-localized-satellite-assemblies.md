---
title: Zabezpečení a lokalizovaná satelitní sestavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b4c153697d95f1496ee3380f63c48d0e4521c05a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54781018"
---
# <a name="security-and-localized-satellite-assemblies"></a>Zabezpečení a lokalizovaná satelitní sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud hlavní sestavení používá silné názvy, musí být stejný soukromý klíč jako hlavní sestavení podepsáno satelitních sestavení. Pokud zadaný klíč veřejného/soukromého pár mezi hlavní a satelitní sestavení, vaše prostředky se neshoduje se nenačte. Další informace o podepisování sestavení naleznete v tématu [jak: Podepsání sestavení silným názvem](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).  
  
 Obecně platí budete muset mít podpisový skupin vaší organizace nebo externí podpisový organizace přihlásit s privátním klíčem. Je to z důvodu citlivosti privátního klíče: přístup je často omezené na několika jednotlivcům. Můžete použít zpožděného podepisování během vývoje. Další informace najdete v tématu [zpožděné podepisování sestavení](http://msdn.microsoft.com/library/9d300e17-5bf1-4360-97da-2aa55efd9070).  
  
## <a name="see-also"></a>Viz také  
 [Důležité informace o zabezpečení sestavení](http://msdn.microsoft.com/library/1b5439c1-f3d5-4529-bd69-01814703d067)   
 [Klíčové koncepty zabezpečení](http://msdn.microsoft.com/library/3cfced4f-ea02-4e66-ae98-d69286363e98)   
 [Představení mezinárodních aplikací založených na rozhraní .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [Lokalizace aplikací](../ide/localizing-applications.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)
