---
title: Práce s 3D modely
description: Přečtěte si o vytváření 3D modelů pomocí editoru modelů v aplikaci Visual Studio, které můžete použít ve vaší hře nebo aplikaci založené na rozhraní DirectX.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fa035091-1354-4d1c-be44-4fb83860466f
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 886d6d24293af9f630e70defff0d95ec791f0edf
ms.sourcegitcommit: a731a9454f1fa6bd9a18746d8d62fe2e85e5ddb1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2020
ms.locfileid: "93133946"
---
# <a name="work-with-3d-models"></a>Práce s 3D modely

Pomocí editoru modelů v aplikaci Visual Studio můžete vytvářet 3D modely. Můžete použít modely ve hře nebo aplikaci založené na rozhraní DirectX.

## <a name="3d-models"></a>3D modely

Trojrozměrné modely definují tvar objektů, které existují ve 3D scéně. Modely můžou být základní objekty Solitary, komplexní objekty, které jsou vytvořené z hierarchií základních objektů, nebo dokonce i celé 3D scény. 3D objekt se skládá z bodů v prostorovém prostoru (známé jako *vrcholy* ), indexů definujících trojúhelníky, řádky nebo jiné primitivní prvky, které jsou tvořeny těmito body, a atributy, které mohou být použity na vrcholech nebo na primitivních základech, například na ploše normální. Kromě toho mohou být některé informace aplikovány na jednotlivé objekty, například na to, který shader a textury přiřadí objektu svůj jedinečný vzhled.

Editor modelů je jediným nástrojem, který potřebujete k vytvoření základních 3D modelů – dokončete s vlastnostmi materiálu, texturami a pixel shadery, které můžete použít ve své hře nebo aplikaci. Nebo můžete vytvořit zástupné modely, které se použijí pro vytváření prototypů a testování před zapojením umělců k finalizaci modelů.

Editor modelů můžete použít také k zobrazení existujících 3D modelů, které byly vytvořeny pomocí integrovaných nástrojů, a upravit je, pokud provedete problémy v uměleckých prostředcích.

## <a name="related-topics"></a>Související témata

|Nadpis|Popis|
|-----------|-----------------|
|[Editor modelů](../designers/model-editor.md)|Popisuje, jak používat Editor modelů pro práci s 3D modely.|
|[Příklady editoru modelů](../designers/how-to-create-a-basic-3-d-model.md)|Obsahuje odkazy na témata, která ukazují, jak používat Editor modelů k provádění běžných úloh 3D modelování.|
