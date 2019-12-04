---
title: 'Postupy: Určení binárního souboru ke spuštění | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: fd3379b9769cfd6bfe1335b12545e635a9bde782
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2019
ms.locfileid: "74778684"
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: Určení binárního souboru ke spuštění

Chcete-li profilovat binární soubory, jako jsou knihovny DLL, je nutné zadat informace v dialogovém okně **\<cílové > stránky vlastností** . Tyto informace označují, kde projekt knihovny DLL může najít volající aplikaci.

1. V **prohlížeč výkonu**klikněte pravým tlačítkem myši na cílový binární soubor a pak klikněte na **vlastnosti**.

2. V dialogovém okně **stránky vlastností** klikněte na vlastnosti **spuštění** .

3. Vyberte zaškrtávací políčko **přepsat vlastnosti projektu** .

4. Do textového pole **spustitelný soubor ke spuštění** zadejte umístění souboru.

5. Do textového pole **argumenty** zadejte argumenty, které jsou požadovány ke spuštění aplikace.

6. Do textového pole **pracovní adresář** zadejte umístění adresáře.

7. Klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
