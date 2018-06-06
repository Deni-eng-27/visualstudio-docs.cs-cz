---
title: 'DA0504: Maximum pracovní sady v bajtech pro profilovaný proces | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0504
- vs.performance.504
- vs.performance.rules.DA0504
ms.assetid: 36e71603-ece7-4000-85fc-9da4eed61bf2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e187d0e0cc1e4c41f96af8f4e76619ff122ac83c
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766227"
---
# <a name="da0504-maximum-working-set-in-bytes-for-the-process-being-profiled"></a>DA0504: Maximum Pracovní sady v bajtech pro profilovaný Proces
|||  
|-|-|  
|Id pravidla|DA0504|  
|Kategorie|Správa prostředků|  
|Metoda profilace|Všechny|  
|Zpráva|Tyto informace byly získány pouze pro informaci. Čítač pracovní sady procesu měří využití fyzické paměti procesem, které jsou profilace. Hodnota hlášené, přes všechny intervaly měření pozorovanou maximální.|  
|Typ pravidla|Informace o|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 10 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Tato zpráva hlásí maximální množství fyzické paměti, v bajtech, které proces aktuálně používá. Pracovní sada procesu představuje stránky z adresního prostoru procesu, které jsou aktuálně umístěny ve fyzické paměti. Toto pravidlo hlásí maximální hodnotu pracovní sady procesu, při vytváření profilu byl aktivní.  
  
 Hodnotu hlášenou obsahuje trvalé stránek ze segmentů sdílené paměti, které proces odkázal. Proces odkazy jsou součástí segmenty sdílené paměti, které se počítají sdílené knihovny DLL. Hodnota procesu pracovní sady může být vyšší než velikost virtuální paměti, který tento proces alokoval z důvodu sdílené paměti segmenty.  
  
 Velikost pracovní sady procesu odráží velikost virtuální paměti proces aktivně používá. Je rovněž ovlivněna množství fyzické paměti (nebo RAM) k dispozici pro spuštění aplikace a kolizí pro tuto fyzickou paměť z jiných spuštěných procesů. Další informace o sadách pracovní proces najdete v tématu [pracovní sady](http://go.microsoft.com/fwlink/?LinkId=177830) v dokumentaci k Windows Správa paměti z webu MSDN.  
  
## <a name="how-to-use-rule-data"></a>Jak používat Data pravidla  
 Toto pravidlo shromáždí tato data měření z objektu sledování výkonu systému Windows a sestavy pouze pro informaci. Použijte ho k porovnání výkonu různých verzí nebo sestavení tohoto programu nebo pochopit výkon aplikace v rámci jiného testovacího scénáře.  
  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [značky zobrazení](../profiling/marks-view.md) profilování data. Najít **Process\Working nastavit** a **Paměť\Stránky/s** čítače sloupce. Vyhledejte maximální hodnota, která **Process\Working nastavit** a porovnat s **Paměť\Stránky/s** hodnotu. Často nastavte maximální pracovní je přidružen interval, ve kterém je ke snížení aktivity vstupně-výstupní operace stránkování, zvlášť pokud je počítač omezené paměti.