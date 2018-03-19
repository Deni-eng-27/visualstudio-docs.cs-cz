---
title: "Postupy: instalace vlastního adaptéru diagnostických dat v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: c0d0f29a84d315ad384a2e7f43c4237ce083871b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>Postupy: Instalace vlastního adaptéru diagnostických dat

Pokud jste vytvořili vlastního adaptéru diagnostických dat nebo vám byly zadány s vlastního adaptéru diagnostických dat použít, můžete nainstalovat vaše sestavení adaptéru diagnostických dat tak, že zkopírujete soubor sestavení pro něj ve správném adresáři na místním počítači.

 Pokud chcete použít pro roli v prostředí vašeho vlastního adaptéru diagnostických dat, je nutné nainstalovat adaptér diagnostických dat na všech počítačích se systémem testovacích agentů, které lze použít pro tuto roli.

 Použijte následující postup k instalaci vaší vlastního adaptéru diagnostických do vhodného umístění. Budete potřebovat oprávnění správce na jakýkoli počítač, který jste nainstalovali adaptér diagnostických dat.

## <a name="installing-a-custom-diagnostic-data-adapter"></a>Instalace vlastního adaptéru diagnostických dat

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>Chcete-li nainstalovat vlastního adaptéru diagnostických dat

1.  Adaptér diagnostických dat použít při spuštění testů na klientský počítač nebo na počítač agenta, zkopírujte všechny soubory z adresáře sestavení v cílovém počítači, na základě cesty instalace na následující adresář:

     *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     Připojené soubory jsou:

    -   Adaptér diagnostických dat sestavení (.dll) (povinné).

    -   Ladění datového souboru (.pdb) pro adaptér (volitelné).

    -   Konfigurační soubor pro adaptér (`<diagnostic data adapter name>.dll.config`), pokud máte výchozí nastavení (volitelné).

    -   Sestavení configuration editor, pokud jste nějakou vytvořili upravit nastavení konfigurace pro adaptér (volitelné). Toto je pouze pro klientské počítače. Počítače agenta nepoužívejte editoru.

    > [!NOTE]
    > I když adaptér diagnostických dat a vaše konfigurace editor můžete vytvořit ve stejném projektu a integrované do stejného sestavení, můžete použít samostatné projekty a vytvořit samostatné sestavení pro ně, pokud dáváte přednost.

     Další informace o tom, jak nakonfigurovat nastavení testu pro používání prostředí při spuštění testů najdete v tématu [shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

2.  Chcete-li vybrat adaptér diagnostických dat pro test, musí nejprve vybrat existujícího nastavení testu nebo vytvořte novou z Microsoft Test Manager nebo Visual Studio a pak vyberte adaptér diagnostických dat na **datové a diagnostické** na kartě nastavení vybrané testů.

3.  Pokud jste vytvořili a nainstalován diagnostických dat adaptér editor konfigurací, nakonfigurujte adaptér diagnostických dat pro testovací nastavení, vyberte **konfigurace** vedle adaptér a ujistěte se žádné změny. Zvolte **Uložit**. Další informace o tom, jak vytvořit konfiguraci editor pro vaše kolekce diagnostických dat najdete v tématu [postupy: vytvoření vlastního editoru dat pro vaše adaptéru diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

4.  Pokud spouštíte testy Microsoft Test Manager, můžete přiřadit tyto otestovat nastavení do testovacího plánu, než můžete spustit testy nebo používat **spustit s možností** příkaz přiřadit nastavení testů a přepsat nastavení testů. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

     Pokud používáte testů ze sady Visual Studio, je nutné nastavit tyto otestovat nastavení jako aktivní. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

5.  Spouštění testů pomocí adaptéru diagnostických dat, vybrané nastavení testu.

## <a name="see-also"></a>Viz také

- [Postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)