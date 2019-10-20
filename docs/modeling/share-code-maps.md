---
title: Export a uložení map kódu
ms.date: 05/16/2018
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 991773953338e38331bad45bfa1149aeb27c748b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72670807"
---
# <a name="share-code-maps"></a>Sdílení map kódu

Mapy kódu můžete uložit jako součást projektu sady Visual Studio, jako obrázek nebo jako soubor ve formátu XPS.

## <a name="share-a-code-map-with-other-visual-studio-users"></a>Sdílení mapy kódu s ostatními uživateli aplikace Visual Studio

Uložte mapu pomocí nabídky **soubor** .

-nebo-

Chcete-li uložit mapu jako součást konkrétního projektu, na panelu nástrojů mapa zvolte možnost **sdílet**  > **přesunout \<CodeMapName >. dgml do**a pak zvolte projekt, kam chcete mapu Uložit.

![Přesunout mapu do jiného projektu](../modeling/media/codemapsmovemapmenu.png)

Visual Studio uloží mapu jako soubor *. dgml* , který můžete sdílet s ostatními uživateli Visual Studio Enterprise a Visual Studio Professional.

> [!NOTE]
> Předtím, než nasdílíte mapu s uživateli, kteří používají Visual Studio Professional, je třeba rozbalit všechny skupiny, zobrazit skryté uzly a odkazy křížové skupiny a načíst všechny odstraněné uzly, které mají jiní uživatelé vidět na mapě. Jinak ostatní uživatelé nebudou moci tyto položky zobrazit.
>
> Při ukládání mapy, která je v projektu modelování nebo byla zkopírována z projektu modelování do jiného umístění, může dojít k následující chybě:
>
> "Nelze uložit *název souboru* mimo adresář projektu. Propojené položky nejsou podporovány.“
>
> Aplikace Visual Studio zobrazí chybu, ale přesto vytvoří uloženou verzi. Chcete-li se této chybě vyhnout, vytvořte mapu mimo projekt modelování. Potom jej můžete uložit do požadovaného umístění. Nebude fungovat, pokud budete chtít soubor pouze zkopírovat do jiného umístění v řešení a potom jej uložit.

## <a name="export-a-code-map-as-an-image"></a>Exportovat mapu kódu jako obrázek

Když exportujete mapu kódu jako obrázek, můžete ho zkopírovat do jiných aplikací, jako je například Microsoft Word nebo PowerPoint.

1. Na panelu nástrojů mapa kódu vyberte **sdílet**  > **e-mailem jako obrázek** nebo **Kopírovat obrázek**.

2. Vložte obrázek do jiné aplikace.

## <a name="export-the-map-as-an-xps-file"></a>Exportovat mapu jako soubor XPS

Pokud exportujete mapu kódu jako soubor XPS, můžete ji zobrazit v prohlížečích XML nebo XAML, jako je Internet Explorer.

1. Na panelu nástrojů mapa kódu vyberte **sdílet**  > **e-maily jako přenosné XPS** nebo **uložte jako přenosný XPS**.

2. Přejděte do umístění, kam chcete soubor uložit.

3. Pojmenujte mapu kódu. Ujistěte se, že je pole **Uložit jako typ** nastaveno na **soubory XPS (\*. XPS)** . Klikněte na tlačítko **Uložit**.

## <a name="see-also"></a>Viz také:

- [Mapování závislostí pomocí map kódu](../modeling/map-dependencies-across-your-solutions.md)