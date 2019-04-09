---
title: 'Postupy: Zahrnutí předpokladů s aplikací ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dcef749068dfb1f13e5b08160a70dda168b771ee
ms.sourcegitcommit: 36f5ffd6ae3215fe31837f4366158bf0d871f7a9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/08/2019
ms.locfileid: "59232850"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Postupy: Zahrnutí předpokladů s aplikací ClickOnce
Před distribucí požadovaného softwaru se [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, musíte nejdřív stáhnout instalační balíčky pro tyto požadavky na vývojovém počítači. Když publikujete aplikaci a zvolte **stáhnout součásti ze stejného umístění, jako je má aplikace**, dojde k chybě, pokud instalační balíčky nejsou uloženy v **balíčky** složky.

> [!NOTE]
>  Přidání instalačního balíčku pro rozhraní .NET Framework naleznete v tématu [Průvodce nasazením rozhraní .NET Framework pro vývojáře](/dotnet/framework/deployment/deployment-guide-for-developers).

##  <a name="Package"></a> K přidání instalačního balíčku pomocí souboru Package.xml

1. V Průzkumníku souborů otevřete **balíčky** složky.

    Výchozí cesta je `%ProgramFiles(x86)%\Microsoft SDKs\ClickOnce Bootstrapper\Packages\`.

2. Otevřete složku požadovaného softwaru, který chcete přidat a potom otevřete složku jazyka nainstalované verze aplikace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (například **en** pro angličtinu).

3. V poznámkovém bloku, otevřete *Package.xml* souboru.

4. Vyhledejte **název** element, který obsahuje **http://go.microsoft.com/fwlink**a zkopírujte adresu URL. Zahrnout **LinkID** část.

   > [!NOTE]
   >  Pokud ne **název** obsahuje element **http://go.microsoft.com/fwlink**, otevřete **Product.xml** soubor v kořenové složce požadovaného softwaru a vyhledejte **fwlink** řetězec.

   > [!IMPORTANT]
   >  Některé požadované softwarové programy mohou mít několik instalačních balíčků (například v 32bitových nebo 64bitových systémech). Pokud je položek víc **název** elementy obsahovat **fwlink**, musí zopakovat zbývající kroky pro každý z nich.

5. Vložte adresu URL do adresního řádku prohlížeče a pak po zobrazení výzvy ke spuštění nebo uložení, zvolte **Uložit**.

    Tento krok stáhne instalační soubor do počítače.

6. Zkopírujte soubor do kořenové složky požadovaného softwaru.

    Například pro předpoklad Windows Installer 4.5 zkopírujte soubor do *\Packages\WindowsInstaller4_5* složky.

    Nyní můžete instalační balíček distribuovat spolu s aplikací.

## <a name="see-also"></a>Viz také:
- [Postupy: Nainstalujte požadavky s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
