---
title: 'Postupy: Hledání e-mailových adres v kontaktech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- e-mail [Office development in Visual Studio], searching
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 178549a815fd9a17377986a5b19e02db12ec76d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60115221"
---
# <a name="how-to-programmatically-search-for-an-email-address-in-contacts"></a>Postupy: Hledání e-mailových adres v kontaktech prostřednictvím kódu programu
  Tento příklad vyhledá složku kontaktů pro kontakty, které mají název domény **example.com** v e-mailové adresy.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_OL_SearchEmail#1](../vsto/codesnippet/CSharp/Trin_OL_SearchEmail/thisaddin.cs#1)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje:

- Kontakty, které mají název domény **example.com** v e-mailové adresy (například `somebody@example.com`), a jejichž křestní jména a příjmení.

## <a name="see-also"></a>Viz také:
- [Práce s položkami kontaktů](../vsto/working-with-contact-items.md)
- [Postupy: Odeslání e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-send-e-mail-programmatically.md)
- [Postupy: Programový přístup ke kontaktům aplikace Outlook](../vsto/how-to-programmatically-access-outlook-contacts.md)
- [Postupy: Přidávání položky ke kontaktům aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)
