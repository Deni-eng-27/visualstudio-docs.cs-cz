---
title: Určení cesty k profilování nástroje příkazového řádku nástroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c89e741e4f854f0426a3b3908b896a8908325684
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56634809"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>Zadejte cestu k nástrojům příkazového řádku pro profilaci
Cesta k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci není přidán do proměnné prostředí PATH. Na 32bitových počítačích nástroje jsou v jednom adresáři. Existují 32bitové a 64bitové verze nástrojů pro profilaci na 64bitových počítačích.

## <a name="32-bit-computers"></a>32bitových počítačích
 Pro nativní kód profileru sady Visual Studio rozhraní API jsou v *VSPerf.dll*. Soubor hlaviček *VSPerf.h*a knihovnu importu *VSPerf.lib*, jsou umístěny v *Microsoft Visual Studio\2017\Team nástroje Tools\PerfSDK* adresář.

 Pro spravovaný kód, okna profilování rozhraní API jsou v *Microsoft.VisualStudio.Profiler.dll*. Tato knihovna DLL se nachází v *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools* adresáře.

## <a name="64-bit-computers"></a>64bitové počítače
 Na 64bitových počítačích zadejte cestu podle cílové platformy profilované aplikace.

-   Pro 32bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2017\Team nástroje Tools\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

-   Pro 64bitové aplikace je výchozí adresář nástrojů profilování:

     (nativní) *Microsoft Visual Studio\2017\Team nástroje Tools\x64\PerfSDK* (spravované) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*