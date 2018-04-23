---
title: 'Postupy: zahrnutí předpokladů s aplikací ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54cdcdb89896662a6d4e474c7df2ee09cea4d8bf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Postupy: Zahrnutí předpokladů s aplikací ClickOnce
Před distribucí požadovaný software s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, musíte nejprve stáhnout balíčky Instalační služby pro tyto požadavky na vývojovém počítači. Při publikování aplikace a zvolte **Stáhnout požadavky ze stejného umístění jako Moje aplikace**, dojde k chybě, pokud balíčky Instalační služby systému nejsou v **balíčky** složky.  
  
> [!NOTE]
>  Chcete-li přidat balíček Instalační služby pro rozhraní .NET Framework, najdete v části [rozhraní .NET Framework Průvodce nasazením pro vývojáře](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).  
  
##  <a name="Package"></a> Chcete-li přidat balíček Instalační služby pomocí Package.xml  
  
1.  V Průzkumníku souborů, otevřete **balíčky** složky.  
  
     Ve výchozím nastavení cesta je C:\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages na 32bitovém systému a C:\Program Files (x86) \Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages na 64bitovém systému.  
  
2.  Otevřete složku pro požadavek, který chcete přidat a poté otevřete složku jazyk pro vaše nainstalovaná verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (například **en** pro angličtinu).  
  
3.  V poznámkovém bloku otevřete **Package.xml** souboru.  
  
4.  Vyhledejte **název** elementu, který obsahuje **http://go.microsoft.com/fwlink**a zkopírujte adresu URL. Zahrnout **LinkID** část.  
  
    > [!NOTE]
    >  Pokud žádné **název** obsahuje element **http://go.microsoft.com/fwlink**, otevřete **Product.xml** souboru do kořenové složky pro požadované součásti a najděte **fwlink** řetězec.  
  
    > [!IMPORTANT]
    >  Některé požadované softwarové programy mohou mít několik instalačních balíčků (například v 32bitových nebo 64bitových systémech). Pokud více **název** prvky obsahují **fwlink**, je nutné opakovat zbývající kroky pro každý z nich.  
  
5.  Vložte adresu URL do adresního řádku prohlížeče a potom, když se zobrazí výzva ke spuštění nebo uložení, vyberte **Uložit**.  
  
     Tento krok stáhne instalační soubor do počítače.  
  
6.  Zkopírujte soubor do kořenové složky požadovaného softwaru.  
  
     V případě požadovaného softwaru Windows Installer 4.5 zkopírujte soubor do složky \Packages\WindowsInstaller4_5.  
  
     Nyní můžete instalační balíček distribuovat spolu s aplikací.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)