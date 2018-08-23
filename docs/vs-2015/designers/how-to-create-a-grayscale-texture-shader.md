---
title: 'Postupy: vytvoření shaderu textury stupňů šedé | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79181d81-44af-445e-9a18-03483dd70260
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9ec147f690612b6094925ae893d42bc4dd5145a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633553"
---
# <a name="how-to-create-a-grayscale-texture-shader"></a>Postupy: Vytvoření shaderu textury stupňů šedé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření shaderu textury stupňů šedé](https://docs.microsoft.com/visualstudio/designers/how-to-create-a-grayscale-texture-shader).  
  
Tento dokument popisuje způsob použití návrháře shaderu a orientovaného grafu shaderu jazyka (DGSL) k vytvoření shaderu textury stupňů šedé. Tento shader změní hodnotu barvy RGB vzorek textury a použije ho spolu s verzí bez úprav alfa hodnotu nastavení konečnou barvu.  
  
## <a name="creating-a-grayscale-texture-shader"></a>Vytvoření shaderu textury stupňů šedé  
 Můžete implementovat shaderu textury stupňů šedé změnou barvy hodnotu vzorku textury před napsáním barvu závěrečný výstup.  
  
 Než začnete, ujistěte se, že **vlastnosti** okno a **nástrojů** jsou zobrazeny.  
  
#### <a name="to-create-a-grayscale-texture-shader"></a>K vytvoření shaderu textury stupňů šedé  
  
1.  Vytvoření shaderu základní textury, jak je popsáno v [postupy: vytvoření shaderu základní textury](../designers/how-to-create-a-basic-texture-shader.md).  
  
2.  Odpojit **RGB** z terminálu **vzorek textury** uzlu z **RGB** z terminálu **konečnou barvu** uzlu. V **vyberte** režimu, zvolte **RGB** z terminálu **vzorek textury** uzel a klikněte na tlačítko **přerušit odkazy**. Díky tomu místo pro uzel, který je přidán v dalším kroku.  
  
3.  Přidat **Odbarvit** uzel do grafu. V **nástrojů**v části **filtry**vyberte **Odbarvit** a přesuňte jej na návrhovou plochu.  
  
4.  Vypočítat hodnotu ve stupních šedi pomocí **Odbarvit** uzlu. V **vyberte** režimu, přesunout **RGB** z terminálu **vzorek textury** uzlu **RGB** z terminálu **Odbarvit**  uzlu.  
  
    > [!NOTE]
    >  Ve výchozím nastavení **Odbarvit** uzel plně desaturates vstupní barva a používá standardní světelnost vah pro převod odstínů šedi. Můžete změnit způsob, jakým **Odbarvit** uzlu se chová tak, že změníte hodnotu **světelnost** vlastnost, nebo jen částečně desaturating vstupní barva. Pokud chcete snížit vstupní barva částečně sytost, zadejte skalární hodnotu v rozsahu [0,1) k **procent** z terminálu **Odbarvit** uzlu.  
  
5.  Hodnota ve stupních šedi barvy se připojte k konečnou barvu. Přesunout **výstup** z terminálu **Odbarvit** uzlu **RGB** z terminálu **konečnou barvu** uzlu.  
  
 Následující obrázek znázorňuje dokončené shader graf a náhled shaderu použitý pro datovou krychli.  
  
> [!NOTE]
>  Na tomto obrázku rovině slouží jako tvar náhled a byl zadán lépe demonstruje účinek shader textury.  
  
 ![Graf shaderu a náhled vlivu](../designers/media/digit-grayscale-effect.png "číslice ve stupních šedi efekt")  
  
 Určité tvary můžou poskytovat lepší verze Preview pro některé shadery. Další informace o zobrazení náhledu shadery v Návrháři shaderu naleznete v tématu [návrháře shaderu](../designers/shader-designer.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití shaderu na 3D Model](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Postupy: exportování shaderu](../designers/how-to-export-a-shader.md)   
 [Editor obrázků](../designers/image-editor.md)   
 [Návrhář shaderů](../designers/shader-designer.md)   
 [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)



