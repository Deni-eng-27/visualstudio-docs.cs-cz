---
title: Omezení instrumentace na konkrétní knihovny DLL | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- performance tools, runtime profiling control window
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: a3584498854e7518e93c4ba00dc019d804b0e8d8
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851018"
---
# <a name="how-to-limit-instrumentation-to-specific-dlls"></a>Postupy: Omezení instrumentace na konkrétní knihovny DLL

Pomocí metody profilace instrumentace můžete omezit shromažďování dat profilování na jednu nebo více knihoven DLL v aplikaci. Chcete-li profilovat jednu nebo více knihoven DLL v aplikaci, vytvořte relaci výkonu, která zahrnuje. soubory *DLL* jako cíle. Můžete určit knihovny DLL, které chcete profilovat jako projekty v řešení aplikace Visual Studio nebo jako nezávislé binární soubory.

## <a name="to-limit-instrumentation-to-specific-dlls-in-a-visual-studio-solution"></a>Omezení instrumentace na konkrétní knihovny DLL v řešení sady Visual Studio

1. Otevřete řešení, které obsahuje knihovnu DLL v aplikaci Visual Studio.

2. V nabídce **analyzovat** vyberte možnost **Spustit Průvodce výkonem**.

3. Jako metodu profilace zvolte **instrumentace** a pak klikněte na **Další**.

4. Z **toho, který z následujících dostupných cílů chcete profilovat?** vyberte název. projekt *knihovny DLL* a potom klikněte na tlačítko **Další**.

5. Kliknutím na tlačítko **Dokončit** ukončíte průvodce a zobrazíte novou relaci výkonu v okně **prohlížeč výkonu** .

6. Klikněte pravým tlačítkem na **cíle** a pak vyberte **Přidat cílový projekt**.

7. V seznamu **Přidat cílový projekt** vyberte spustitelný projekt, který chcete použít pro cvičení knihovny DLL.

     Nepovinný parametr. Můžete přidat všechny projekty knihoven DLL, které chcete profilovat.

8. Chcete-li zabránit shromažďování dat pro přidaný projekt, klikněte pravým tlačítkem myši na název projektu a poté zrušte zaškrtnutí políčka **instrumentace** .

## <a name="to-specify-specific-dlls-to-profile-as-independent-binaries"></a>Určení specifických knihoven DLL pro profilování jako nezávislých binárních souborů

1. Otevřete sadu Visual Studio.

2. V nabídce **analyzovat** vyberte možnost **Spustit Průvodce výkonem**.

3. Z **toho, který z následujících dostupných cílů byste chtěli profilovat**, vyberte **profil knihovny DLL (. DLL)** a poté klikněte na tlačítko **Další**.

4. Na druhé stránce průvodce proveďte následující kroky:

    - Zadejte cestu a název souboru. soubor *DLL* , který chcete profilovat v **cestě knihovny DLL**. Můžete také kliknout na tlačítko se třemi tečkami (...) a vyhledat soubor v dialogovém okně **Knihovna dynamického propojení do profilu** . Všimněte si, že je nutné zadat kopii. soubor *DLL* , který bude spuštěn spustitelným souborem (.* soubor exe*), který vyberete další.

    - Zadejte cestu a název souboru spustitelného souboru (.* exe*), který bude vyvolávat. *Knihovna DLL* v **cestě ke spustitelnému souboru**. Můžete také kliknout na tlačítko se třemi tečkami (...) a vyhledat soubor v dialogovém okně **spustitelného souboru, který se má spustit** .

    - Nepovinný parametr. Zadejte argumenty příkazového řádku, které chcete předat spustitelnému souboru v **argumentech příkazového řádku**. V případě potřeby zadejte pracovní adresář pro aplikaci v **pracovním adresáři**.

    - Klikněte na **Next** (Další).

5. Jako metodu profilace zvolte **instrumentace** a pak klikněte na **Další**.

6. Kliknutím na tlačítko **Dokončit** ukončíte průvodce a zobrazíte novou relaci výkonu v okně **prohlížeč výkonu** .

7. Nepovinný parametr. Pro přidání dalších. soubory *DLL* , klikněte pravým tlačítkem na **cíle** a pak vyberte **Přidat cílový binární soubor**. Vyberte soubory z dialogového okna **Přidat cílový binární soubor** .

    > [!NOTE]
    > Nezadávejte spustitelný soubor (.* exe*) soubor, který vykonává knihovny DLL.

## <a name="see-also"></a>Viz také

[Řízení shromažďování dat](../profiling/controlling-data-collection.md) 
 [Postupy: omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)
