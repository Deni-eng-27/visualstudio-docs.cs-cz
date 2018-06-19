---
title: Určení stavu příkazu pomocí spolupráce – sestavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4989910fdec968a4a05e2459e6625ee2c15fd9a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128163"
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Určení stavu příkazu pomocí spolupráce – sestavení
VSPackage musí udržovat přehled o stavu příkazů, které může zpracovat. Prostředí nelze určit, když se změní na příkaz zpracovávaných v rámci vaší VSPackage povolený nebo zakázaný. Je zodpovědností vaší VSPackage k informování o stavy příkazového prostředí, například stav Obecné příkazy, jako **Vyjmout**, **kopie**, a **vložení**.  
  
## <a name="status-notification-sources"></a>Stav zdrojů oznámení  
 Prostředí obdrží informace o příkazech prostřednictvím VSPackages <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda, která je součástí VSPackage implementace systému <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Volání prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda VSPackage pod dvě podmínky:  
  
-   Když uživatel otevře hlavní nabídky nebo z kontextové nabídky (kliknutím pravým tlačítkem myši), provede v prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metodu na všechny příkazy v této nabídce určit jejich stav.  
  
-   Když VSPackage požaduje, aby prostředí aktualizovala aktuální uživatelské rozhraní (UI). K tomu dochází jako příkazy, které jsou aktuálně viditelné pro uživatele, například **Vyjmout**, **kopie**, a **vložení** seskupování na standardním panelu nástrojů, stane povolené a zakázané v odpovědi na akce v kontextu a uživatele.  
  
 Vzhledem k tomu, že prostředí hostitelem více VSPackages, výkon prostředí služby by nepřijatelně snížit, pokud bylo potřeba dotazovat jednotlivých VSPackage k určení stavu příkazu. Místo toho vaší VSPackage by měl aktivně zprávu, prostředí svém uživatelském rozhraní se změní v době změny. Další informace o upozornění na aktualizace najdete v tématu [aktualizace uživatelského rozhraní](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Selhání oznámení stavu  
 Selhání vaší VSPackage oznámit prostředí změnu stavu příkazu můžete umístit uživatelského rozhraní v nekonzistentním stavu. Mějte na paměti, že některé z vaší nabídky nebo kontextu příkazy nabídky můžete umístit na panelu nástrojů uživatelem. Proto aktualizace uživatelského rozhraní jenom v případě, otevře se nabídka nabídky nebo kontextu není dost.  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementace](../../extensibility/internals/command-implementation.md)