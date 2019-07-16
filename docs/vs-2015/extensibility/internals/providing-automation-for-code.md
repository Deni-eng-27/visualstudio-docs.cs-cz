---
title: Poskytování automatizace pro kód | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2e4d47a72adf787f5d560374e1c44743004d25f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203237"
---
# <a name="providing-automation-for-code"></a>Poskytování automatizace pro kód
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vytvoření modelu automatizace kódu se nevyžaduje. Sada SDK prostředí neposkytuje ukázku to udělat. Přehled o tom, modely kódu, najdete v článku <xref:EnvDTE.CodeModel> objektu.  
  
 K implementaci modelu kódu, je nutné implementovat všechna rozhraní, které jsou určeny vnitřní datovou strukturu. Objekty musí být odvozen od `IDispatch` třídy.  
  
 Objekty, které můžete rozšířit <xref:EnvDTE.CodeModel> a <xref:EnvDTE.FileCodeModel>, jsou k dispozici na <xref:EnvDTE.Project> objektu a vypadat nějak takto:  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 Můžete se rozhodnout k implementaci jenom `CodeModel` nebo `FileCodeModel` rozhraní v objektu, kterou vrátíte z vaší `Project` a <xref:EnvDTE.ProjectItem> objekty. Zadejte všechny funkce z tohoto rozhraní, která je vhodná pro váš systém projektu.  
  
 Pokud chcete přidat funkce, jako je například metody nebo vlastnosti, které nejsou k dispozici prostřednictvím standardu `CodeModel` a `FileCodeModel` rozhraní, vytvořte vlastní rozhraní, která dědí z normy. Ujistěte se, že dokument s váš systém projektu tak, že koncoví uživatelé vědí, vyhledejte ho. Vrátí standardní rozhraní, ale uživatel může volat `QueryInterface` metody nebo přetypování do vašeho rozhraní, pokud je známo, že existují.  
  
## <a name="see-also"></a>Viz také  
 [Přehled modelu automatizace](../../extensibility/internals/automation-model-overview.md)
