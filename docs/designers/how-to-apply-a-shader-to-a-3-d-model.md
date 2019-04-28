---
title: 'Postupy: Použití shaderu na 3D Model'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 896cc39ae3e9f53d96a30f6485c40afc8259e270
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62845040"
---
# <a name="how-to-apply-a-shader-to-a-3d-model"></a>Postupy: Použití shaderu na 3D model

Tento článek popisuje způsob použití Editoru modelů pro použití orientovaného grafu Shader Language (DGSL) shaderu na 3D model.

## <a name="apply-a-shader-to-a-3d-model"></a>Použití shaderu na 3D model

Použít efekt shaderu na 3D model nabízí zajímavé vzhled.

Než začnete, ujistěte se, že **vlastnosti** se zobrazí okno.

1. Začněte s 3D scéně, který obsahuje jeden nebo více modelů. Pokud nemáte k dispozici vhodný 3D scény, vytvořit jak je popsáno v [jak: Vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md). Musíte mít také DGSL shader, který můžete použít pro model. Pokud nemáte k dispozici vhodný shaderu, vytvořit jak je popsáno v [jak: Vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md) a ujistěte se, že jste uložili ji do souboru předtím, než budete pokračovat.

2. V **vyberte** režimu, vyberte model, na který chcete použít shaderu a pak v **vlastnosti** okno v **Filename** vlastnost **efekt**  skupiny vlastností zadejte DGSL shader, který má být použita k modelu.

Tady je model, který je použit efekt základní barvy:

![3&#45;scény D, která demonstruje účinek základní barvy](../designers/media/digit-3d-model-effect.png)

Po použití shaderu na model, lze jej otevřít v Návrháři shaderu tak, že vyberete model a pak v **vlastnosti** okno v **(rozšířené)** vlastnost **efekt**skupiny vlastností, vyberete symbol tří teček (**...** ) tlačítko.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)
- [Postupy: Vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md)
- [Editor modelů](../designers/model-editor.md)
- [Návrhář shaderů](../designers/shader-designer.md)