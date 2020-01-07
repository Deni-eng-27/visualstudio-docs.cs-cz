---
title: 'Postupy: Vytvoření základní textury'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0222e8bf-d29f-421b-9b1f-123d500fa179
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 916be87824a86e96d6fcb791cf8181d70e1e8104
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75589449"
---
# <a name="how-to-create-a-basic-texture"></a>Postupy: Vytvoření základní textury

Tento článek ukazuje, jak pomocí editoru obrázků vytvořit základní texturu, včetně následujících aktivit:

- Nastavení velikosti textury

- Nastavení barev popředí a pozadí

- Používání alfa kanálu (transparentnost)

- Používání nástrojů **vyplnit** a **tři tečky**

- Nastavení vlastností nástroje

## <a name="create-a-basic-texture"></a>Vytvoření základní textury

Editor obrázků můžete použít k vytvoření a úpravě obrázků a textur pro vaši hru nebo aplikaci.

Následující kroky ukazují, jak vytvořit texturu, která představuje cíl "Bullseye". Až budete hotovi, textura by měla vypadat jako na následujícím obrázku. Pro lepší znázornění průhlednosti v textuře byl Editor obrázků nakonfigurován tak, aby používal zelený a monitorový vzor k zobrazení.

![Cíl "Bullseye" s transparentností zobrazený zeleně](../designers/media/digit-bullseye-texture-in-editor.png)

Než začnete, ujistěte se, že se zobrazilo okno **vlastnosti** . Pomocí okna **vlastnosti** můžete nastavit velikost obrázku, změnit vlastnosti nástroje a určit barvy při práci.

### <a name="create-a-bullseye-target-texture"></a>Vytvořit cílovou texturu "Bullseye"

1. Vytvořte texturu, se kterou chcete pracovat. Informace o tom, jak přidat texturu do projektu, naleznete v tématu [Editor obrázků](../designers/image-editor.md#get-started).

2. Nastavte velikost obrázku na 512x512 pixelů. V okně **vlastnosti** nastavte hodnoty vlastnosti **Width** a **Height** na `512`.

3. Na panelu nástrojů Editor obrázků vyberte nástroj **Fill** Tool. V okně **vlastnosti** se nyní zobrazí vlastnosti nástroje **Fill** spolu s vlastnostmi obrázku.

4. Nastavte barvu popředí na plně průhlednou černou. V okně **vlastnosti** ve skupině vlastnost **barvy** vyberte tlačítko **popředí**. Nastavte hodnoty vlastností **R**, **G**, **B**a a vedle výběru barvy na `0`.

5. Na panelu nástrojů Editor obrázků zvolte nástroj **Fill** , stiskněte a podržte klávesu **SHIFT** a vyberte libovolný bod v obrázku. Použití klávesy **SHIFT** způsobí, že hodnota alfa barvy výplně nahradí barvu v obrázku. v opačném případě se hodnota alfa používá k prolnutí barvy výplně spolu s barvou v obrázku.

    > [!IMPORTANT]
    > Tento krok společně s výběrem barvy v předchozím kroku zajistí, že se bude připravit základní obrázek pro cílovou texturu "Bullseye", kterou nakreslíte. Když je obrázek vyplněn průhledným černým a vzhledem k tomu, že ohraničením cíle je černé – k cíli nebudou žádné žádné artefakty s aliasy.

6. Na panelu nástrojů Editor obrázků vyberte nástroj **Elipsa** .

7. Nastaví barvu popředí na zcela neprůhlednou černou. Nastavte hodnoty vlastností **R**, **G**a **B** na `0` a **hodnotu vlastnosti,** která se má `255`.

8. Nastaví barvu pozadí na plně neprůhlednou bílou. V okně **vlastnosti** ve skupině vlastnost **barvy** vyberte možnost **pozadí**. Nastavte hodnoty vlastností **R**, **G**, **B**a a na `255` .

9. Nastaví šířku obrysu elipsy. V okně **vlastnosti** ve skupině vlastnost **vzhled** nastavte hodnotu vlastnosti **Width** na `8`.

10. Ujistěte se, že je povolená ochrana proti aliasům. V okně **vlastnosti** ve skupině vlastností **vzhled** se ujistěte, že je nastavena vlastnost **anti-alias** .

11. Pomocí nástroje **Elipsa** nakreslete kružnici z souřadnice pixelu `(3, 3)` na souřadnici pixel `(508, 508)`. Chcete-li nakreslit kruh snadněji, můžete stisknout a podržet klávesu **SHIFT** při kreslení.

    > [!NOTE]
    > Souřadnice obrazového bodu aktuálního umístění ukazatele se zobrazí ve stavovém řádku aplikace Visual Studio.

12. Změní barvu pozadí. Nastavte **R** na `44`, **G** na `165`, **B** na **`211`a na** `255`.

13. Nakreslete další kružnici z souřadnice pixelu `(64, 64)` na souřadnici pixel `(448, 448)`.

14. Změňte barvu pozadí zpátky na zcela neprůhlednou bílou. Nastavte **R**, **G**, **B** **a a na `255`** .

15. Nakreslete další kružnici z souřadnice pixelu `(128, 128)` na souřadnici pixel `(384, 384)`.

16. Změní barvu pozadí. Nastavte **R** na `255`, **G** a **B** **na `64`a na** `255`.

17. Nakreslete další kružnici z souřadnice pixelu `(192, 192)` na souřadnici pixel `(320, 320)`.

Cílová textura "Bullseye" je dokončena. Tady je finální obrázek, který je zobrazený s průhledností.

![Kompletní textura cíle "Bullseye"](../designers/media/gfx_image_demo_bullseye.png)

V dalším kroku můžete vygenerovat úrovně MIP pro tuto texturu. Informace najdete v tématu [Postup: vytváření a úpravy úrovní MIP](../designers/how-to-create-and-modify-mip-levels.md).

## <a name="see-also"></a>Viz také:

- [Editor obrázků](../designers/image-editor.md)
