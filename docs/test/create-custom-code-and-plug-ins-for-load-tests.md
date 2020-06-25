---
title: Vytvoření vlastního kódu a modulů plugin pro zátěžové testování
ms.date: 10/19/2016
ms.topic: how-to
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3c060dc9bd50c6dc49777e9114eadae4d6267d92
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85288673"
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Vytvoření vlastního kódu a modulů plugin pro zátěžové testování

Vlastní modul plug-in používá kód, který píšete a připojujete k testu zatížení nebo testu výkonnosti webu. Pomocí rozhraní API zátěžového testu a rozhraní API testu výkonnosti webu můžete vytvořit vlastní moduly plug-in pro rozšíření na integrované funkce. Do zátěžového testu můžete přidat několik modulů plug-in.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="tasks"></a>Úlohy

|Úlohy|Přidružená témata|
|-|-----------------------|
|**Vytvoření vlastního modulu plug-in pro zátěžový test**: pomocí rozhraní API zátěžového testu můžete vytvořit vlastní modul plug-in pro přidání více funkcí testování do zátěžového testu.|-   [Postupy: použití rozhraní API zátěžového testu](../test/how-to-use-the-load-test-api.md)<br />-   [Postupy: Vytvoření modulu plug-in zátěžového testu](../test/how-to-create-a-load-test-plug-in.md)|
|**Vytvořte vlastní modul plug-in pro test výkonnosti webu:** Pomocí rozhraní API testu výkonnosti webu můžete vytvořit vlastní modul plug-in pro přidání více funkcí testování do testu výkonnosti webu, včetně na úrovni žádosti. Můžete také vytvořit test webové služby.<br /><br /> Kromě toho můžete vytvořit modul plug-in zapisovače webu, který může upravit test výkonnosti webu po jeho nahrání, ale ještě před tím, než se zobrazí v Prohlížeč výsledků testů výkonu webu.|-   [Postupy: použití rozhraní API testu výkonnosti webu](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Postupy: Vytvoření modulu plug-in testu výkonnosti webu](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Postupy: Vytvoření modulu plug-in na úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Postupy: vytvoření testu webové služby](../test/how-to-create-a-web-service-test.md)<br />-   [Postupy: Vytvoření modulu plug-in pro záznam](../test/how-to-create-a-recorder-plug-in.md)|
|**Přidání funkcí uživatelského rozhraní do prohlížeče webového výkonu výsledky testů Viewer:** Pomocí doplňku sady Visual Studio můžete přidat další funkce uživatelského rozhraní do prohlížeče webového výkonu Výsledky testů Viewer.|-   [Postupy: vytvoření doplňku sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Vytvoření vlastního editoru těla protokolu http:** Můžete vytvořit vlastní editor pro úpravu binárních nebo řetězcových odpovědí HTTP XML z webové služby.|-   [Postupy: Vytvoření vlastního editoru těla protokolu HTTP pro Editor testu výkonnosti webu](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Referenční informace

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Viz také

- [Analyzovat výsledky zátěžového testu](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)
