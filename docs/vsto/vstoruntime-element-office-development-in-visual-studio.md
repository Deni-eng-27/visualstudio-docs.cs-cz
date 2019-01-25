---
title: '&lt;vstoruntime –&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 98f483748cce9c3a053c800f9bdd6e0f3d651da2
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54876197"
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoruntime –&gt; – element (vývoj pro Office v sadě Visual Studio)
  `vstoRuntime` Elementu `vstav3` obor názvů obsahuje podporovanou verzi sady Visual Studio Tools for Office runtime pro konkrétní řešení Office.

## <a name="syntax"></a>Syntaxe

```xml
<vstoRuntime
    release
    version
    supportUrl />
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `vstoRuntime` Element je povinný a je v `vstav3` oboru názvů. Pokud řešení pro Office podporuje dvě verze nástroje Visual Studio Tools pro systém Office runtime, existují dva `vstoRuntime` prvky v manifestu aplikace.

 `vstoRuntime` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`release`|Povinný parametr. Verze sady Visual Studio Tools for Office runtime.|
|`version`|Povinný parametr. Číslo verze sady Visual Studio Tools for Office runtime.|
|`supportUrl`|Volitelné. Odkaz na umístění instalace sady Visual Studio Tools for Office runtime.|

 `vstoRuntime` neobsahuje žádné prvky.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, `vstoRuntime` elementu v manifestu aplikace pro řešení Office nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

```xml
<vstav3:vstoRuntime
    release="VSTOR40Beta1"
    version="10.0.20303"
    supportUrl="http://www.microsoft.com" />
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
