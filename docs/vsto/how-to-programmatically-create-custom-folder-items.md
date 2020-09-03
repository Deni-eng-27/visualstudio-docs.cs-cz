---
title: 'Postupy: vytváření vlastních položek složek prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], creating
- Outlook folders [Office development in Visual Studio], custom
author: John-Hart
ms.author: johnhart
ms.workload:
- office
ms.openlocfilehash: 652768fa23902722a9b071a4ad12de4cbf774ab6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546026"
---
# <a name="how-to-programmatically-create-custom-folder-items"></a>Postupy: vytváření vlastních položek složek prostřednictvím kódu programu
  Tento příklad vytvoří novou složku v aplikaci systém Microsoft Office Outlook. Pro název složky se používá jméno přihlášeného uživatele.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_CustFolderItem#1](../vsto/codesnippet/CSharp/Trin_OL_CustFolderItem/thisaddin.cs#1)]

## <a name="see-also"></a>Viz také
- [Práce se složkami](../vsto/working-with-folders.md)
- [Postupy: Přidání položky do kontaktů aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
- [Postupy: vytváření událostí prostřednictvím kódu programu](../vsto/how-to-programmatically-create-appointments.md)
