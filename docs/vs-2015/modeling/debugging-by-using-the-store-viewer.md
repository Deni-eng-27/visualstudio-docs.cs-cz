---
title: Ladění pomocí prohlížeče úložiště | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
ms.assetid: 0178db2e-ae99-4ed3-9b87-8620fa9fa8e4
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a870c66b1c14dc6ddf3e38fb6e5be8c116be3573
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72654881"
---
# <a name="debugging-by-using-the-store-viewer"></a>Ladění pomocí Prohlížeče ukládání
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V prohlížeči úložiště můžete kontrolovat stav *úložiště* , které používá [!INCLUDE[dsl](../includes/dsl-md.md)] . V prohlížeči úložiště se zobrazí všechny prvky doménového modelu, které jsou v konkrétním úložišti, spolu s vlastnostmi elementu a odkazy mezi prvky.

## <a name="opening-store-viewer"></a>Otevírání prohlížeče úložiště
 Když jste v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] experimentálním sestavení, zastavte svůj kód na zarážce, kde instance úložiště obsahuje informace o modelu. Pak otevřete prohlížeč Storu zadáním následujícího příkazu v **příkazovém** okně:

```
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);
```

> [!NOTE]
> Je nutné nahradit `mystore` názvem vaší instance úložiště. Také Pokud přidáte obor názvů do kódu, můžete zadat příkaz pro zobrazení prohlížeče úložiště bez plně kvalifikovaného oboru názvů:
>
> `using Microsoft.VisualStudio.Modeling.Diagnostics;`
>
> `…`
>
> `StoreViewer.Show(mystore);`

 `Show`Metoda má několik přetížení. Jako parametr můžete zadat instanci úložiště nebo oddíl.

 Alternativně můžete vložit řádek kódu, který zobrazí prohlížeč úložiště kdekoli ve vašem kódu, kde parametr, který předáte `Show` metodě, je v oboru. Tato akce zobrazí prohlížeč úložiště, když se řádek kódu spustí jako snímek obsahu úložiště.

### <a name="using-store-viewer"></a>Použití prohlížeče úložiště
 Když se otevře prohlížeč úložiště, zobrazí se nemodální model Windows Forms okno, jak ukazuje následující obrázek.

 ![](../modeling/media/storeviewer2.png "storeviewer2") Prohlížeč úložiště

 Prohlížeč Store má tři podokna: levé podokno, pravé horní podokno a pravé dolní podokno. Levé podokno je stromové zobrazení typů v rámci `DomainDataDirectory` člena úložiště. Pokud rozbalíte uzel oddílu a kliknete na prvek, zobrazí se v pravém horním podokně vlastnosti prvku. Pokud je element propojen s jinými prvky, zobrazí se další prvky v pravém dolním podokně. Pokud dvakrát kliknete na prvek v pravém dolním podokně, element je zvýrazněn v levém podokně.

## <a name="see-also"></a>Viz také
 [Navigace v modelu a aktualizace modelu v kódu programu](../modeling/navigating-and-updating-a-model-in-program-code.md)
