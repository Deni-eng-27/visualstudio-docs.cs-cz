---
title: "Hlediska zabezpečení vizualizéru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, security
- security [Visual Studio], visualizers
ms.assetid: cdd86bd5-b729-409b-a7c6-374efa091eb1
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47ed06179d09996ac1b35cd3d2dd5d6cb99296d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visualizer-security-considerations"></a>Hlediska zabezpečení vizualizéru
Zápis Vizualizéru zahrnuje možných bezpečnostních hrozeb. Pro tyto potenciální hrozby aktuálně neexistuje žádné známé zneužití, ale vývojáři by měl mít na paměti je a trvat příslušná bezpečnostní opatření, podle postupu popsaného tady, pro ochranu proti zneužití budoucí.  
  
 Ladicí program vizualizérech vyžadují větší oprávnění než je povoleno podle aplikace s částečnou důvěryhodností. Vizualizérech nenačte, když se zastavil v kódu s částečným vztahem důvěryhodnosti. Chcete-li ladit pomocí vizualizéru, musíte spustit kód s úplným vztahem důvěryhodnosti.  
  
## <a name="possible-malicious-debuggee-component"></a>Možné škodlivé součásti pozastaven  
 Vizualizérech obsahovat minimálně dvě třídy: jeden na straně ladicího programu a jeden na straně pozastaven. V samostatné sestavení umístit do adresáře speciální často nasazených vizualizérech, ale mohou být i mimo ladění načíst. V takovém případě ladicího programu trvá kód mimo ladění a spouští v ladicím programu s úplným vztahem důvěryhodnosti.  
  
 Spuštění kódu na straně pozastaven s úplným vztahem důvěryhodnosti změní problematické, pokud není plně důvěryhodný pro ladění. Pokud vizualizéru se pokusí načíst částečnou důvěryhodností sestavení z ladění do ladicího programu, Visual Studio vizualizér přeruší.  
  
 Méně závažné ohrožení zabezpečení, ale stále existuje. Ladicí program straně, která byla načtena z jiného zdroje (není pozastaven) můžete přidružit straně pozastaven. Na straně pozastaven pak můžete sdělit, které důvěryhodný straně ladicí program k provádění akcí jeho jménem. Pokud důvěryhodné třída ladicí program na straně zpřístupňuje mechanismus "odstranění tohoto souboru", například pozastaven částečným vztahem důvěryhodnosti může vyvolat tento mechanismus při jeho vizualizér vyvolá uživatele.  
  
 Aby se minimalizoval toto ohrožení zabezpečení, mějte na paměti rozhraní vystavené vaší vizualizér.  
  
## <a name="see-also"></a>Viz také  
 [Architektura vizualizéru](../debugger/visualizer-architecture.md)   
 [Postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md)   
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)