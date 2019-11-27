---
title: Použití emulátoru Express ke spuštění a ladění cloudové služby Azure v místním počítači | Microsoft Docs
description: Použití emulátoru Express ke spuštění a ladění cloudové služby v místním počítači
author: mikejo5000
manager: jillfra
ms.assetid: 73108f98-a552-4817-b7a1-551367b71906
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 03/06/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: d89762511e88e296a51c781c6a403c2dd227ed4f
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74293259"
---
# <a name="using-emulator-express-to-run-and-debug-an-azure-cloud-service-on-a-local-machine"></a>Spuštění a ladění cloudové služby Azure na místním počítači pomocí expresního emulátoru
Pomocí nástroje emulátor Express můžete testovat a ladit cloudovou službu bez spuštění sady Visual Studio jako správce. Nastavení projektu můžete nastavit tak, aby v závislosti na požadavcích vaší cloudové služby používala buď emulátor Express, nebo úplný emulátor. Další informace o plném emulátoru najdete v tématu [spuštění aplikace Azure v emulátoru služby COMPUTE](/azure/storage/common/storage-use-emulator).

## <a name="using-emulator-express-in-visual-studio"></a>Použití emulátoru Express v aplikaci Visual Studio
Při vytváření projektu Azure v sadě Azure SDK 2,3 nebo novější se automaticky použije emulátor Express. U existujících projektů, které byly vytvořeny pomocí starší verze sady Azure SDK, vyberte pomocí následujících kroků příkaz emulátor Express:

1. Vytvořte nebo otevřete v sadě Visual Studio projekt cloudové služby Azure.

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt a v místní nabídce vyberte možnost **vlastnosti**.

1. Na stránkách vlastností projektů vyberte kartu **Web** .

    ![Vlastnosti projektu cloudové služby Azure](./media/vs-azure-tools-emulator-express-debug-run/web-properties.png)

1. V části **místní vývojový server**vyberte **použít IIS Express možnosti**.

1. V části **emulátor**vyberte **použít emulátor Express**.
   
1. Pokud chcete spustit emulátor Express, spusťte na příkazovém řádku tento příkaz: 

    ```
    csrun.exe /useemulatorexpress
    ```

## <a name="emulator-express-limitations"></a>Expresní omezení emulátoru
Následující problémy jsou známá omezením emulátoru Express: 

- Emulátor Express není kompatibilní s webovým serverem IIS.
- Vaše cloudová služba může obsahovat víc rolí, ale každá role je omezená na jednu instanci.
- Nemůžete získat přístup k číslům portů nižším než 1000. Pokud používáte poskytovatele ověřování, který obvykle používá port pod 1000, může být nutné změnit tuto hodnotu na číslo portu, které je vyšší než 1000.
- Všechna omezení, která platí pro emulátor služby Azure COMPUTE, platí také pro expresní emulátor. Například nemůžete mít více než 50 instancí role na jedno nasazení. Další informace o emulátoru výpočtů Azure najdete v tématu [spuštění aplikace Azure v emulátoru služby COMPUTE](https://go.microsoft.com/fwlink/p/?LinkId=623050).

## <a name="next-steps"></a>Další kroky
[Ladění Azure Cloud Services](vs-azure-tools-debugging-cloud-services-overview.md)
