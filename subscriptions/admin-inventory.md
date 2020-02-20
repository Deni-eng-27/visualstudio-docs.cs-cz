---
title: Inventář předprodukčních prostředí | Visual Studio Marketplace
author: evanwindom
ms.author: lank
manager: lank
ms.date: 02/17/2020
ms.topic: conceptual
description: Další informace o responsibilty správců pro provádění předprodukčních inventářů
ms.openlocfilehash: 6d7dd3b49c11e94ffa09bc07bd745582f348763d
ms.sourcegitcommit: 374f5ec9a5fa18a6d4533fa2b797aa211f186755
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2020
ms.locfileid: "77476732"
---
# <a name="inventory-of-pre-production-environment"></a>Inventář předprodukčního prostředí
Předplatná sady Visual Studio zjednodušují správu prostředků, a to pomocí počítání uživatelů místo zařízení.

Správci sady Visual Studio musí přiřadit předplatná sady Visual Studio **konkrétním pojmenovaným jednotlivcům**. Konvence pojmenování, jako je například dev1, Dev2 nebo použití názvů týmů, jako je "FeatureTeam", nejsou **povoleny**.

Tady je několik způsobů, jak zjednodušit inventarizaci předprodukčního prostředí:
- Zkontrolujte přiřazení uživatelů. Společnost Microsoft poskytuje web s názvem [portál pro správu sady Visual Studio](https://manage.visualstudio.com/) , který vám může pomáhat sledovat přiřazení předplatných sady Visual Studio.
- K vypsání uživatelů můžete použít místní nebo cloudovou službu Active Directory. Pokud ke správě přístupu uživatelů používáte službu Active Directory, možná budete moct identifikovat vývojové a testovací uživatele podle jejich členství v adresáři.
- Pro inventarizaci systémů použijte automatizované nástroje. Je také možné, že budete muset použít nástroj inventáře softwaru, který vám umožní spravovat softwarové prostředky a rozlišovat předprodukční prostředí z produkčních prostředí. Mnoho zákazníků s Microsoft System Center vytvoří konvence pro pojmenování, které vám pomůžou automatizovat tuto část procesu inventarizace.
- Získejte nápovědu k ručnímu odsouhlasení. Zařadíte své zaměstnance, který vám umožní sjednotit vývoj a testování uživatelů pomocí vývojového a testovacího prostředí.

## <a name="resources"></a>Zdroje a prostředky
- [Dokument white paper k licencování sady Visual Studio](https://visualstudio.microsoft.com/wp-content/uploads/2019/06/Visual-Studio-Licensing-Whitepaper-May-2019.pdf)
- [Podpora správy a předplatných sady Visual Studio](https://visualstudio.microsoft.com/support/support-overview-vs)
- [Multilicenční podmínky](https://www.microsoft.com/licensing/product-licensing/products.aspx)

## <a name="next-steps"></a>Další kroky
Další informace o zodpovědnostech pro správce:
- [Odpovědnosti správce](admin-responsibilities.md)
- [Správa velkých týmů a externích dodavatelů](manage-teams.md)
- [Sledování přiřazení uživatelů a zpracování objednávek](assignments-orders.md)
- Použití [maximálního využití](maximum-usage.md) ke sledování závazků nákupu

## <a name="see-also"></a>Viz také
- [Dokumentace k sadě Visual Studio](https://docs.microsoft.com/visualstudio/)
- [Dokumentace ke službě Azure DevOps](https://docs.microsoft.com/azure/devops/)
- [Dokumentace k Azure](https://docs.microsoft.com/azure/)
- [Dokumentace k Microsoft 365](https://docs.microsoft.com/microsoft-365/)

