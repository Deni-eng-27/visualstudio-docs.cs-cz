---
title: Odstranit přiřazení předplatného sady Visual Studio na portálu pro správu předplatných | Microsoft Docs
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: e49242bc-e9f2-49e8-8caa-f574d508aba6
ms.date: 10/26/2020
ms.topic: how-to
description: Zjistěte, jak můžou správci odstraňovat přiřazení předplatného na portálu pro správu předplatných sady Visual Studio.
ms.openlocfilehash: 22a1c55bcaef436d1a29eb84b93a57f407114a1e
ms.sourcegitcommit: f1d47655974a2f08e69704a9a0c46cb007e51589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2020
ms.locfileid: "92904477"
---
# <a name="delete-assignments-in-visual-studio-subscriptions"></a>Odstranit přiřazení v předplatných sady Visual Studio
Pokud již předplatitel nevyžaduje předplatné sady Visual Studio, například když odejdou ze společnosti, dokončí projekt nebo přepne na novou roli úlohy, můžete odebrat jejich předplatné a přiřadit ho někomu jinému. Upozorňujeme, že při opětovném přiřazení předplatného dojde k resetování všech výhod předplatitele.  Nový uživatel bude moci vyžádat všechny neoprávněné klíče a zobrazit dříve požadované klíče, ale omezení deklarací identity nebudou **resetována** .  Pro organizace, které mají smlouvy Enterprise (EA), se všechny výhody, které použil původní uživatel, jako je třeba školení Pluralsight, resetují. 

Podívejte se na toto video nebo si přečtěte, jak odstranit přiřazení.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yG2q]

## <a name="delete-a-subscription-assignment"></a>Odstraní přiřazení předplatného.
1. Klikněte na jméno předplatitele, kterého chcete odebrat. Chcete-li vybrat více odběratelů k odebrání, můžete kliknout na kroužek vlevo od názvu předplatitele a vybrat si ho.  Případně můžete podržet klávesu **CTRL** a kliknout na každého předplatitele, kterého chcete odebrat. Chcete-li odebrat řadu předplatitelů, klikněte na první, stiskněte klávesu **SHIFT** a klikněte na poslední z nich.  Stisknutím **kombinace kláves CTRL + a** vyberte a odeberte všechny předplatitele. V tomto příkladu se odstraní tři předplatitelé – oranžová, Kai a Madison –. 
2. Pokud chcete vybrané odběratele odstranit, klikněte na **Odstranit** .
3. Jakmile se zobrazí zpráva s výzvou k potvrzení odstranění, klikněte na tlačítko **OK** .
   > [!div class="mx-imgBorder"]
   > ![Odstranit předplatitele](_img/delete-license/delete-subscribers.png "Vyberte uživatele, které chcete odstranit, a klikněte na Odstranit. Pomocí kláves CTRL a Shift můžete vybrat více odběratelů.")

   > [!NOTE]
   > Hromadné odstranění pomocí šablony není k dispozici. 
   >
   > Pokud jste přidali přiřazení předplatného prostřednictvím Azure Active Directory skupin zabezpečení, může trvat až 24 hodin, než se odstranění aktualizuje na portálu pro správu.  Další informace o použití skupin Azure Active Directory ke správě předplatných najdete v [našem článku](assign-license-bulk.md#use-azure-active-directory-groups-to-assign-subscriptions) . 

## <a name="see-also"></a>Viz také
- [Dokumentace k sadě Visual Studio](/visualstudio/)
- [Dokumentace ke službě Azure DevOps](/azure/devops/)
- [Dokumentace k Azure](/azure/)
- [Dokumentace k Microsoft 365](/microsoft-365/)

## <a name="next-steps"></a>Další kroky
- Potřebujete změnit předplatné, aniž byste ho odstranili?  Informace o tom, jak [Upravit odběry](edit-license.md)
- Nápovědu k vyhledání konkrétního předplatného najdete v tématu [hledání předplatného](search-license.md).
- Potřebujete vytvořit seznam všech vašich předplatných?  Podívejte se prosím na [Export předplatných](exporting-subscriptions.md).