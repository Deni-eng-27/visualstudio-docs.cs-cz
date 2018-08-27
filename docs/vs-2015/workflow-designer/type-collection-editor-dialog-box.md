---
title: Dialogové okno Editor typu kolekce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 34b8129b5a0b1fe27a7e4e6c178ddace638e5ffc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667937"
---
# <a name="type-collection-editor-dialog-box"></a>Dialogové okno Editor typu kolekce
**Editor typu kolekce** dialogové okno umožňuje přidat známé typy, které **odeslat** a **Receive** aktivity. Toto dialogové okno se také používá k přidání argumentů obecného typu **InvokeMethod** aktivity. Když se použije pro **odeslat** a **Receive** aktivity přidat známé typy, **Editor typu kolekce** dialogovému oknu vyžaduje přidání typ být jedinečný. Pokud se přidá duplicitní typ a kliknutím se potvrzené změny **OK**, vrátí chybovou zprávu. Když se použije pro **InvokeMethod** aktivity přidáte argumenty obecného typu, **Editor typu kolekce** dialogové okno umožňuje přidání duplicitní typy.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../includes/crabout-md.md)] známé typy, najdete v článku [známé typy kontraktů dat](http://msdn.microsoft.com/library/1a0baea1-27b7-470d-9136-5bbad86c4337).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **kolekci typů** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Seznam typů**|Seznam typů, které byly přidány nebo odebrány.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Chcete-li přenést až Editor typu kolekce  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Funkce přineste si Editor typu kolekce pro odesílání a příjem aktivity  
  
1.  Vyberte **odeslat** nebo **Receive** aktivity v návrhovém zobrazení.  
  
2.  Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.  
  
3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **KnownTypes** vlastnost.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Chcete-li přenést až Editor kolekce typu aktivity InvokeMethod  
  
1.  Vyberte **InvokeMethod** aktivity v návrhovém zobrazení.  
  
2.  Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.  
  
3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **parametry GenericTypeArguments** vlastnost.