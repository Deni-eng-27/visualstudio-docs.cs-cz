---
title: Hierarchie v aplikaci Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- hierarchies, Visual Studio IDE
- IDE, hierarchies
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cdbb8a0e58f6b1e5bc6e32f8c319d1480c4db4b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80708192"
---
# <a name="hierarchies-in-visual-studio"></a>Hierarchie v sadě Visual Studio
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Integrované vývojové prostředí (IDE) zobrazuje projekt jako *hierarchii*. V integrovaném vývojovém prostředí je hierarchie stromem uzlů, kde každý uzel má sadu přidružených vlastností. *Hierarchie projektu* je kontejner, který obsahuje položky projektu, relace položky a přidružené vlastnosti a příkazy položek.

 V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nástroji můžete spravovat hierarchie projektu pomocí rozhraní hierarchie, <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> . <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>Rozhraní přesměrovává příkazy, které jste vyvolali z položek projektu, do příslušného okna hierarchie namísto standardní obslužné rutiny příkazu.

## <a name="project-hierarchies"></a>Hierarchie projektu
 Každá hierarchie projektu obsahuje položky, které lze zobrazit a upravit. Tyto položky se liší v závislosti na typu projektu. Databázový projekt může například obsahovat uložené procedury, zobrazení databáze a databázové tabulky. Projekt programovacího jazyka na druhé straně bude nejspíš zahrnovat zdrojové soubory a soubory prostředků pro rastrové obrázky a dialogová okna. Hierarchie můžou být vnořené, což vám dává větší flexibilitu při vytváření hierarchie projektu.

 Při vytváření nového typu projektu řídí typ projektu úplnou sadu položek, které lze v ní upravovat. Projekty však mohou obsahovat položky, pro které nemají podporu úprav. Například Visual C++ projekty mohou obsahovat soubory HTML, i když Visual C++ neposkytuje žádný přizpůsobený editor pro typ souboru HTML.

 Hierarchie spravují persistenci položek, které obsahují. Implementace hierarchie musí řídit jakékoli speciální vlastnosti, které mají vliv na trvalost položek v rámci hierarchie. Například pokud položky reprezentují objekty v úložišti namísto souborů, implementace hierarchie musí řídit trvalost těchto objektů. Rozhraní IDE sám směruje hierarchii tak, aby uložila položky v souladu s uživatelským vstupem, ale rozhraní IDE neřídí žádné akce potřebné k uložení těchto položek. Místo toho je projekt v řízení.

 Když uživatel otevře položku v editoru, hierarchie, která řídí tuto položku, je vybrána a stávají se aktivní hierarchií. Vybraná hierarchie Určuje sadu příkazů, které jsou k dispozici pro tuto položku. Sledování fokusu uživatele tímto způsobem umožňuje, aby hierarchie odrážela aktuální kontext uživatele.

## <a name="see-also"></a>Viz také
- [Typy projektů](../../extensibility/internals/project-types.md)
- [Výběr a měna v integrovaném vývojovém prostředí](../../extensibility/internals/selection-and-currency-in-the-ide.md)
- [Ukázky VSSDK](https://github.com/Microsoft/VSSDK-Extensibility-Samples)
