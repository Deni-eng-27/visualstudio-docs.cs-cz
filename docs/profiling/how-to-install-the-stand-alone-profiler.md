---
title: 'Postupy: Instalovat samostatný Profiler | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- performance tools, installing stand-alone profiler
- profiling tools, stand-alone profiler
ms.assetid: cae81c95-83cd-4ab6-8a98-84ef977a2f6d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 949787ae06d9599f0132c15a0205f034419a312d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54928595"
---
# <a name="how-to-install-the-stand-alone-profiler"></a>Postupy: Instalace samostatného profileru
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytuje příkazový řádek na základě samostatného profileru, který můžete spustit bez nutnosti instalace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí. Tato situace nastane, pokud počítač není nebo nemůže mít nainstalované prostředí pro vývoj. Například byste neměli instalovat prostředí pro vývoj na produkčním webovém serveru.  
  
> [!NOTE]
>  Při použití samostatného profileru pro shromažďování dat pro webový server ASP.NET, [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) čára se doporučuje přes [VSPerfCmd](../profiling/vsperfcmd.md) nástroj.  
  
### <a name="to-install-the-stand-alone-profiler"></a>Instalace samostatného profileru  

1. Stáhněte si [Performance Tools for Visual Studio](https://visualstudio.microsoft.com/downloads/?q=performance+tools#performance-tools-for-visual-studio-2017).

1. Vyhledejte instalační program samostatné profilu (*vs_standaloneprofiler.exe*) které jste stáhli nástroje Sledování výkonu a spustíme ji.
  
2. Přidání cesty pro *vsintr.exe* a *msdis150.dll* do systémové cesty.  
  
   > [!NOTE]
   >  Chcete-li získat cestu k nástrojů pro profilaci, naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého. 
  
3. Na příkazovém řádku zadejte **VSInstr**.  
  
   > [!NOTE]
   >  Pokud se zobrazí informace o využití pro vsinstr.exe, všechno je správně nastavené. Pokud se zobrazí chyba s oznámením vsinstr.exe nebo některá z jeho závislostí nebyla nalezena, ujistěte se, že máte vaší cesty nastavena správně, jak je popsáno v kroku 2.  
  
4. Nastavit server symbolů tak, že nastavíte váš **_NT_SYMBOL_PATH** proměnnou **symsrv\*symsrv.dll\*c:\localcache\*http://msdl.microsoft.com/download/symbols**  
  
5. Po nastavení serveru symbolů pomocí proměnných prostředí systému spuštění příkazového řádku profileru nástroje z nového příkazového řádku. To umožňuje nové proměnné prostředí se projeví. V okně příkazového řádku zadejte následující příkaz:  
  
    **spuštění COMSPEC %**  
  
   > [!NOTE]
   >  Podrobné pokyny o tom, jak nastavit server balíčku symbolů najdete v tématu [jak: Referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md).  
  
6. Použití [VSPerfReport](../profiling/vsperfreport.md) nástroj pro serializaci symbolů do souboru dat profilování (.vsp). Použití **Summary VSPerfReport/packsymbols** přepínače. Pokud nemáte symboly vložen do vašeho datového souboru, ujistěte se, že máte nastavení proměnné prostředí _NT_SYMBOL_PATH.  
  
## <a name="see-also"></a>Viz také:  
 [Profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [Návod: Příkazový řádek profilování pomocí vzorkování](../profiling/walkthrough-command-line-profiling-using-sampling.md)   
 [Návod: Příkazový řádek, profilace s použitím instrumentace](/visualstudio/profiling/command-line-profiling-of-stand-alone-applications)   
 [Postupy: Referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)