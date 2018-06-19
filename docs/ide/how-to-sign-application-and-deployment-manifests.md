---
title: 'Postupy: podepsání manifestů aplikace a nasazení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- manifests [Visual Studio]
- code signing [Visual Studio], Authenticode
- deployment manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- ClickOnce deployment [Visual Studio], signing assemblies
- key files [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 64173505-8bfb-41cf-a0de-b9075173f3a2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5cee4f7ff8438c1e20f39a24e9e439e7507d655b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31951723"
---
# <a name="how-to-sign-application-and-deployment-manifests"></a>Postupy: podepsání manifestů aplikace a nasazení

Pokud chcete publikovat aplikace pomocí ClickOnce – nasazení, manifestů aplikace a nasazení musí být podepsané páru veřejného a privátního klíče RSA a podepsaný pomocí technologie Authenticode. Manifesty můžete podepsat pomocí certifikátu z úložiště certifikátů Windows nebo soubor klíče.

 Další informace o nasazení pomocí technologie ClickOnce najdete v tématu [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md).

 Podepisování manifestů ClickOnce je pro volitelné *.exe*– na základě aplikací. Další informace najdete v části "Generovat nepodepsané manifesty" tohoto dokumentu.

 Informace o vytváření soubory klíčů najdete v tématu [postupy: vytvoření páru veřejného a privátního klíče RSA](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).

> [!NOTE]
> [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podporuje pouze soubory klíčů Personal Information Exchange (PFX), které mají *.pfx* rozšíření. Nicméně můžete vybrat jiné typy certifikátů z úložiště certifikátů aktuálního uživatele systému Windows kliknutím **zvolit z úložiště** na **podpisování** stránky vlastností projektu.

## <a name="to-sign-application-and-deployment-manifests-using-a-certificate"></a>K podepsání aplikace a nasazení manifesty pomocí certifikátu

1.  Přejděte do okna vlastností projektu (klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**, nebo typ **projektu vlastnosti** v **Snadné spuštění** okno, nebo klikněte na tlačítko **Alt**+**Enter** uvnitř **Průzkumníku řešení** okno). Na **podpisování** vyberte **podepsání manifestů ClickOnce** zaškrtávací políčko.

2.  Klikněte **zvolit z úložiště** tlačítko.

     **Vyberte certifikát, který** se zobrazí dialogové okno a zobrazí obsah úložiště certifikátů systému Windows.

    > [!TIP]
    > Pokud kliknete na tlačítko **kliknutím sem můžete zobrazit vlastnosti certifikátu**, **podrobnosti certifikátu** zobrazí se dialogové okno. Toto dialogové okno obsahuje podrobné informace o certifikátu a obsahuje další možnosti. Můžete kliknout na **certifikáty** na zobrazení další informace nápovědy.

3.  Vyberte certifikát, který chcete použít k podepsání manifestů.

4.  Kromě toho můžete zadat adresu serveru časové razítko v **adresa URL serveru časové razítko** textové pole. Toto je server, který obsahuje časové razítko určující, když byl podepsán manifest.

## <a name="to-sign-application-and-deployment-manifests-using-an-existing-key-file"></a>K podepsání aplikace a nasazení manifesty pomocí existujícího souboru s klíčem

1.  Na **podpisování** vyberte **podepsání manifestů ClickOnce** zaškrtávací políčko.

2.  Klikněte **vybrat ze souboru** tlačítko.

     **Vyberte soubor** zobrazí se dialogové okno.

3.  V **vyberte soubor** dialogové okno, přejděte do umístění souboru klíče (*.pfx*), kterou chcete použít a pak klikněte na **otevřete**.

    > [!NOTE]
    > Tato volba podporuje pouze soubory, které mají *.pfx* rozšíření. Pokud máte soubor klíče nebo certifikát v jiném formátu, uložte ho v úložišti certifikátů systému Windows a vyberte certifikát, který je popsaný v předchozím postupu. Vybraný certifikát účel by měly obsahovat, podepisování kódu.

     **Zadejte heslo k otevření souboru** zobrazí se dialogové okno. (Pokud *.pfx* soubor je již uložen v úložišti certifikátů systému Windows, nebo není chráněn heslem, nezobrazí se výzva k zadání hesla.)

4.  Zadejte heslo pro přístup k souboru s klíčem a stiskněte klávesu **Enter**.

## <a name="to-sign-application-and-deployment-manifests-using-a-test-certificate"></a>K podepsání aplikace a nasazení manifesty pomocí testovacího certifikátu

1.  Na **podpisování** vyberte **podepsání manifestů ClickOnce** zaškrtávací políčko.

2.  Chcete-li vytvořit nový certifikát pro testování, klikněte na tlačítko **vytvořit testovací certifikát** tlačítko.

3.  V **vytvořit testovací certifikát** dialogovém okně zadejte heslo, které pomáhá zabezpečit váš testovací certifikát.

## <a name="generate-unsigned-manifests"></a>Generovat nepodepsané manifesty

Podepisování manifestů ClickOnce je pro volitelné *.exe*– na základě aplikací. Následující postupy ukazují, jak vygenerovat nepodepsané manifesty ClickOnce.

> [!IMPORTANT]
> Nepodepsané manifesty můžete zjednodušit vývoje a testování vaší aplikace. Nepodepsané manifesty však zavést významné bezpečnostní riziko v produkčním prostředí. Pouze na nabídnuté pomocí nepodepsané manifesty, pokud vaše aplikace ClickOnce běží na počítačích v rámci sítě intranet, který je naprosto izolované od Internetu, nebo jiné zdroje škodlivý kód.

 Ve výchozím nastavení ClickOnce automaticky generuje podepsané manifesty, pokud jeden nebo více souborů, které jsou výslovně vyloučeny z generované hodnoty hash. Jinými slovy, publikování aplikace výsledky v podepsané manifesty, pokud všechny soubory jsou součástí hodnotu hash, i když **podepsání manifestů ClickOnce** zaškrtnutí políčka.

### <a name="to-generate-unsigned-manifests-and-include-all-files-in-the-generated-hash"></a>Generovat nepodepsané manifesty a zahrnout všechny soubory generované hodnoty hash

1.  Pokud chcete vygenerovat nepodepsané manifesty, které zahrnují všechny soubory v hodnotu hash, musíte nejprve publikovat aplikace společně s podepsané manifesty. Proto nejprve podepsání manifestů ClickOnce jedním z předchozích postupech a pak publikujte aplikaci.

2.  Na **podpisování** zrušte zaškrtnutí políčka **podepsání manifestů ClickOnce** zaškrtávací políčko.

3.  Resetujte verzi publikování, je k dispozici pouze jedna verze vaší aplikace. Ve výchozím nastavení Visual Studio automaticky zvýší číslo revize verze publikování pokaždé, když publikování aplikace. Další informace najdete v tématu [postupy: verze publikování ClickOnce sadu](../deployment/how-to-set-the-clickonce-publish-version.md).

4.  Publikování aplikace.

### <a name="to-generate-unsigned-manifests-and-exclude-one-or-more-files-from-the-generated-hash"></a>Generovat nepodepsané manifesty a vyloučit jeden nebo více souborů z generované hodnoty hash

1.  Na **podpisování** zrušte zaškrtnutí políčka **podepsání manifestů ClickOnce** zaškrtávací políčko.

2.  Otevřete **soubory aplikace** dialogové okno a sadu **Hash** k **vyloučit** pro soubory, které chcete vyloučit z generované hodnoty hash.

    > [!NOTE]
    > Vyloučení souboru z hodnoty hash konfiguruje ClickOnce k zakázání automatického podepisování manifestů, takže není nutné nejprve publikovat s podepsané manifesty, jak je znázorněno v předchozím postupu.

3.  Publikování aplikace.

## <a name="see-also"></a>Viz také

- [Sestavení se silným názvem](/dotnet/framework/app-domains/strong-named-assemblies)
- [Postupy: vytvoření páru veřejného a privátního klíče RSA](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair)
- [Stránka podepisování, Návrhář projektu](../ide/reference/signing-page-project-designer.md)
- [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)