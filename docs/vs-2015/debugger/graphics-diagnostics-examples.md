---
title: Příklady Diagnostika grafiky | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 45dd86b2-801e-4b07-a8c4-7bd25641d7f8
caps.latest.revision: 36
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 14b4ac689109e29baa4ee06c668b208d0d5227b0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68159720"
---
# <a name="graphics-diagnostics-examples"></a>Příklady diagnostiky grafiky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto příklady ukazují, jak ladit problémy vykreslování v aplikacích založených na rozhraní DirectX pomocí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Diagnostika grafiky.  
  
## <a name="capturing-graphics-information"></a>Zachycení informací grafiky  
 Než budete moct použít Diagnostika grafiky k diagnostice problémů s vykreslováním v aplikaci, musíte zachytit informace grafiky z aplikace, když je spuštěná. Informace o grafikách se dají zachytit z aplikace, která je spuštěná místně, nebo z aplikace, která běží na vzdáleném počítači nebo jiném zařízení. Tyto návody ukazují, jak můžete zachytit grafické informace z aplikace ručně nebo programově:  
  
- [Návod: Zaznamenání grafických informací](../debugger/walkthrough-capturing-graphics-information.md)  
  
- [Návod: Zaznamenání grafických informací prostřednictvím kódu programu](../debugger/walkthrough-capturing-graphics-information-programmatically.md)  
  
## <a name="use-graphics-diagnostics-with-an-arm-based-device"></a>Použití Diagnostika grafiky se zařízením s procesorem ARM  
 Můžete použít Diagnostika grafiky k ladění aplikace Direct3D na zařízení s procesorem ARM pomocí vzdáleného ladění. Další informace najdete v tématu [Postupy: použití Diagnostika grafiky se zařízením ARM](../debugger/how-to-use-graphics-diagnostics-with-an-arm-device.md).  
  
## <a name="playing-back-graphics-information"></a>Přehrávání informací o grafice  
 Po zachycení informací grafiky ze spuštěné aplikace můžete přehrát zachycené události a diagnostikovat problémy s vykreslováním. Pro přehrání můžete použít svůj počítač pro vývoj nebo můžete použít vzdálený počítač nebo zařízení, ke kterému jste připojeni. Další informace najdete v tématu [Postup: změna Diagnostika grafiky počítač pro přehrávání](../debugger/how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="debugging-missing-objects"></a>Ladění chybějících objektů  
 Chybějící objekt (nebo objekty) je jedním z nejběžnějších potíží s vykreslováním, které vývojáři grafiky můžou vyzkoušet. Tento druh problému může být obtížné diagnostikovat, protože několik různých druhů chyb může způsobit, že objekt zdánlivě zmizí. Obvyklé příčiny chybějících objektů zahrnují nesprávně nakonfigurovaný stav zařízení, problémy s transformací geometrie objektu nebo nesprávně nakonfigurované grafické kanály.  
  
 Tyto scénáře ukazují, jak lze pomocí Diagnostika grafiky zjistit, proč objekt chybí, a najít kód, který je zodpovědný.  
  
- [Návod: Chybějící objekty z důvodu stavu zařízení](../debugger/walkthrough-missing-objects-due-to-device-state.md)  
  
- [Návod: Chybějící objekty z důvodu použití vertex shaderu](../debugger/walkthrough-missing-objects-due-to-vertex-shading.md)  
  
- [Návod: Chybějící objekty z důvodu nesprávné konfigurace kanálu](../debugger/walkthrough-missing-objects-due-to-misconfigured-pipeline.md)  
  
## <a name="debugging-rendering-errors"></a>Ladění chyb vykreslování  
 Objekt (nebo objekty), který nemá správný vzhled, je dalším běžným problémem, který vývojáři grafiky můžou vyzkoušet. Tento druh problému může být obtížné diagnostikovat, protože špatný vzhled a jeho příčina může být v rozsahu od velmi zjevné – svázat špatnou texturu – je to velmi jemné – chyba v kódu shaderu nebo neočekávaná interakce mezi shadery. Některé problémy mohou být způsobeny kombinací chyb.  
  
 Tady je scénář, který předvádí, jak můžete pomocí Diagnostika grafiky sledovat problém s nedrobným vykreslováním, který je způsobený menší chybou shaderu:  
  
- [Návod: Ladění chyb vykreslování způsobených stínováním](../debugger/walkthrough-debugging-rendering-errors-due-to-shading.md)  
  
## <a name="debugging-compute-shaders"></a>Ladění výpočetních shaderů  
 Diagnostika grafiky můžete použít k ladění jader DirectCompute výpočetního shaderu, které generují nesprávné výsledky. Pomocí DirectCompute můžete použít výpočetní výkon GPU k paralelnímu provádění výpočtů velkého množství datových prvků. U určitých druhů problémů může použití GPU mnohem rychleji probíhat, než i dobře optimalizovaný kód procesoru. Tradiční ladicí program ale nedokáže detekovat kód, který běží na GPU. Ladění tohoto druhu kódu vyžaduje specializované nástroje, které jsou často specifické pro dodavatele a nemusí být dobře integrovány se sadou Visual Studio. Aby se ladění výpočetního shaderu v celé řadě GPU shodovalo, Diagnostika grafiky zachytává události odeslání DirectCompute – kromě událostí vykreslování Direct3D, takže můžete používat známé nástroje k ladění problémů v kódu COMPUTE-shader.  
  
 Pokud se jedná o scénář, který ukazuje, jak ladit problém simulace, který je způsoben chybou ve výpočetním shaderu, přečtěte si [Návod: použití Diagnostika grafiky k ladění výpočetního shaderu](../debugger/walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader.md).
