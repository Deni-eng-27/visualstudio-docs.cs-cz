---
title: Určení cesty k profilování nástroje příkazového řádku nástroje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7fadcff84c4b927a7718d7d4ad1311918ae0f18a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60066933"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Určení cesty k nástrojům příkazového řádku pro profilaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cesta k [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkazového řádku nástrojů pro profilaci není přidán do proměnné prostředí PATH. Na 32bitových počítačích nástroje jsou v jednom adresáři. Existují 32bitové a 64bitové verze nástrojů pro profilaci na 64bitových počítačích.  
  
## <a name="32-bit-computers"></a>32bitových počítačích  
 Na 32bitových počítačích, je výchozí adresář nástrojů profilování *jednotka*\Program Files\Microsoft 11.0\Team nástroje nástroje Visual Studio.  
  
## <a name="64-bit-computers"></a>64bitové počítače  
 Na 64bitových počítačích zadejte cestu podle cílové platformy profilované aplikace.  
  
- Pro 32bitové aplikace je výchozí adresář nástrojů profilování:  
  
     *Jednotka*\Program soubory (x86) \Microsoft Visual Studio 11.0\Team nástroje nástroje  
  
- Pro 64bitové aplikace je výchozí adresář nástrojů profilování:  
  
     *Drive*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64
