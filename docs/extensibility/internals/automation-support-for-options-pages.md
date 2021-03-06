---
title: Podpora automatizace pro stránky možností | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe45238948d5b4cdebbf9f002f6b242515e7622e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709934"
---
# <a name="automation-support-for-options-pages"></a>Podpora automatizace pro stránky možností
Sady VSPackage mohou poskytnout dialogová okna vlastních **možností** do nabídky **nástroje** (stránky**možností nástrojů** ) v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a mohou je zpřístupnit modelu automatizace.

## <a name="tools-options-pages"></a>stránky Možnosti nástrojů
 Chcete-li vytvořit stránku **možností nástroje** , VSPackage musí poskytnout implementaci uživatelského ovládacího prvku vrácenou do prostředí prostřednictvím implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> metody VSPackage. (Nebo, pro spravovaný kód, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> metoda.)

 Je volitelná, ale důrazně se doporučuje, aby byl přístup k této nové stránce povolen pomocí modelu automatizace. Můžete to udělat pomocí následujících kroků:

1. Rozšiřuje <xref:EnvDTE._DTE.Properties%2A> objekt pomocí implementace objektu odvozeného pro rozhraní IDispatch.

2. Vraťte implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> metody (nebo spravovaného kódu <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> metody) na objekt odvozený od rozhraní IDispatch.

3. Když příjemce automatizace volá <xref:EnvDTE._DTE.Properties%2A> metodu na stránce vlastností vlastní **Možnosti** , prostředí používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> metodu k získání automatizované implementace stránky **možností nástrojů** .

4. Automatizační objekt sady VSPackage je pak použit k poskytnutí všech <xref:EnvDTE.Property> vrácených funkcí <xref:EnvDTE._DTE.Properties%2A> .

   Ukázku implementace vlastní **Možnosti nástrojů** naleznete v tématu [VSSDK Samples](https://github.com/Microsoft/VSSDK-Extensibility-Samples).

## <a name="see-also"></a>Viz také
- [Vystavení objektů projektu](../../extensibility/internals/exposing-project-objects.md)
