---
title: Vnořování projektů | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 814780fa8e7e57a022a75b2e09115cfa55a1b8be
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80707035"
---
# <a name="nesting-projects"></a>Vnoření projektů
Vývojáři podnikových aplikací, kteří používají váš balíček VS, mohou pohodlně seskupit podobné typy projektů dohromady [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pomocí *vnoření projektu*. Například projekt šablony organizace používá vnořené projekty k seskupení projektů do kategorií. Projekty obchodní fasády, projekty webového uživatelského rozhraní a tak dále jsou seskupeny do jedné kategorie.

 V tomto scénáři neexistuje žádné omezení počtu projektů, které může vývojář vnořit do jednotlivých nadřazených projektů, i když vývojář může programově poskytnout omezení. Tento typ seskupení lze také nastavit jako rekurzivní, v takovém případě mohou být projekty stejného typu jako podřízený projekt vnořeny do podřízené položky, aby se staly dílčím projektem podřízeného prvku, který je dílčím projektem nadřazeného objektu.

 Vnoření projektu není vnitřní součástí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] . Je nutné napsat kód pro povolení vnoření a dílčího projektu vnoření do podřízených projektů. Nadřazený projekt je speciální VSPackage nebo typ projektu, vytvořený a registrovaný pomocí vlastního identifikátoru GUID, který obsahuje kód, který je vyžadován pro implementaci vnořování projektu.

 Příklad, jak vnořovat projekty, naleznete v tématu [How to: Implementing Nested Projects](../../extensibility/internals/how-to-implement-nested-projects.md).

## <a name="nested-projects-example"></a>Příklad vnořených projektů
 ![Řešení vnořených projektů](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects") Příklad vnořených projektů

## <a name="see-also"></a>Viz také
- [Důležité informace pro uvolnění a opětovné načtení vnořených projektů](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)
- [Podpora průvodce pro vnořené projekty](../../extensibility/internals/wizard-support-for-nested-projects.md)
- [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)
- [Implementace zpracování příkazů pro vnořené projekty](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)
- [Filtrování dialogového okna Přidat položku pro vnořené projekty](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)
- [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Kontextové parametry](../../extensibility/internals/context-parameters.md)
- [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)
