---
title: Příkaz dostupnosti | Dokumentace Microsoftu
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- commands, context
- menu items, visibility contexts
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30a4992bed527b017f66f42067f88ec127fb9ed3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070601"
---
# <a name="command-availability"></a>Dostupnost příkazu

Kontext sady Visual Studio Určuje, které příkazy jsou k dispozici. Kontext můžete měnit v závislosti na aktuální projekt, aktuální editor, rozšíření VSPackages, která jsou načtena a další aspekty integrovaného vývojového prostředí (IDE).

## <a name="command-contexts"></a>Příkaz kontextů

Následující příkaz kontexty jsou nejčastěji:

- INTEGROVANÉ VÝVOJOVÉ PROSTŘEDÍ: Příkazy poskytované rozhraní IDE jsou vždy k dispozici.

- VSPackage: Rozšíření VSPackages můžete definovat, kdy jsou příkazy k zobrazení nebo skrytí.

- Projekt: Projekt příkazy se zobrazují jenom pro aktuálně vybraný projekt.

- Editor: Najednou může být aktivní pouze jeden editor. Příkazy z aktivního editoru jsou k dispozici. Editor úzce spolupracuje se službou language. Služba jazyka musí zpracovat příkazy v kontextu editoru přidružené.

- Typ souboru: Editor může načíst více než jeden typ souboru. Dostupné příkazy můžete měnit v závislosti na typu souboru.

- Aktivní okno: Poslední okno aktivní dokument nastavuje uživatelský kontext rozhraní (UI) pro vazby klíčů. Panel nástrojů, který má klíč vazby tabulku, která vypadá podobně jako interní webový prohlížeč, ale také nastavit kontextu uživatelského rozhraní. Pro dokument s kartami s více windows jako je například HTML editor má každá karta jiný příkaz kontextu identifikátor GUID. Po registraci panelu nástrojů je vždy k dispozici na **zobrazení** nabídky.

- Kontext uživatelského rozhraní: Kontexty uživatelského rozhraní jsou určeny hodnoty <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> třídy, například <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionBuilding_guid> při sestavení řešení nebo <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Debugging_guid> když je aktivní ladicí program. Kontexty více uživatelského rozhraní může být aktivní ve stejnou dobu.

## <a name="define-custom-context-guids"></a>Definovat vlastní místní GUID

Pokud příslušný příkaz kontextu, již není definovaný identifikátor GUID, můžete definovat jeden v vašeho balíčku VSPackage a pak naprogramovat tak být aktivní nebo neaktivní podle potřeby řídit viditelnost příkazů:

1.  Zaregistrovat GUID kontextu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> metody.

2.  Získat stav kontextu GUID voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metody.

3.  Zapnutí a vypnutí GUID kontextu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> metody.
   
> [!CAUTION]
> Ujistěte se, že vaše VSPackage nemá vliv na všechny existující kontext identifikátory GUID vzhledem k tomu, že ostatní rozšíření VSPackages může záviset na ně.

## <a name="see-also"></a>Viz také:

- [Kontextové objekty výběru](../../extensibility/internals/selection-context-objects.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)