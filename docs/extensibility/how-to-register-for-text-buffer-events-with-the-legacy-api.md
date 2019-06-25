---
title: 'Postupy: Zaregistrujte se na textové vyrovnávací paměti události s rozhraním API starší verze | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 10f1dbbc50535c1b0fd297f99c359ea8b0511c68
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321446"
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>Postupy: Zaregistrujte se na události vyrovnávací paměti textu pomocí starší verze rozhraní API
Pokud vyrovnávací paměť textu přistupujete pomocí starší verze rozhraní API, byste měli zaregistrovat pro události vyrovnávací paměti textu, jak je znázorněno v následujícím postupu.

## <a name="to-advise-text-buffer-events"></a>Radit události vyrovnávací paměť textu

1. Z ukazatele na jedno z rozhraní na <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>, volání `QueryInterface` ukazatele na <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.

2. Volání <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> metoda a předejte jí rozhraní ID událostí, pro které chcete zaregistrovat.

     Například, pokud chcete zaregistrovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, pak předejte ID IID_IVsTextLinesEvents rozhraní.

     Vrací ukazatel na textovou vyrovnávací paměť <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní pro objekt bodu příslušné připojení.

3. Pomocí tohoto ukazatele, zavolejte <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> metodu ukazatel na implementaci rozhraní události, pro kterou chcete zaregistrovat, například `IVsTextLinesEvents` rozhraní.

     Vrátí prostředí do souboru cookie, který potom slouží k zastavení naslouchá událostem voláním <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> metody.

## <a name="see-also"></a>Viz také:
- [Události vyrovnávací paměti textu ve starší verzi rozhraní API](../extensibility/text-buffer-events-in-the-legacy-api.md)