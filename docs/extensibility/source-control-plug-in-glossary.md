---
title: Glosář modulu Plug-in ovládací prvek zdroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0df624a27513fa0eb18b2643bb7c680d71d94c0c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722355"
---
# <a name="source-control-plug-in-glossary"></a>Glosář modulu plug-in zdrojového kódu
Užitečné následující pojmy a definice se vztahují k dokumentaci zdrojového ovládacího prvku modulu Plug-in SDK.

## <a name="definitions"></a>Definice
 Když uživatel provede změny do funkční kopie vrácení se změnami, uživatel musí odeslat změny z pracovní kopie do úložiště správy centrální zdrojového kódu. Tím se vytvoří nová revize souboru, který je k dispozici jiným uživatelům. Tento proces se nazývá vrácení se změnami.

 V rámci žádosti o pracovní kopie v úložišti informuje úložiště váš pokus o úpravu ho rezervovat. Pracovní kopie odráží stav projektu od okamžiku, kdy je rezervován.

 Klient A program, který využívá systém správy zdrojového kódu. Pro účely této dokumentace je integrované vývojové prostředí sady Visual Studio.

 Komentář A zpráva popisující změny, které uživatel může připojit k revizi při provádění operaci správy zdrojových kódů.

 Konflikt A situaci, když dva uživatelé pokoušejí k vrácení se změnami změny do stejné oblasti stejného souboru. Obvykle musí být provedeno sloučení.

 A na straně klienta místní složku se označuje jako adresář. Toto je kopírování, ve kterém uživatel ve skutečnosti provádí změny. Může být mnoho pracovních kopií daného projektu. obecně každý vývojář má svůj vlastní kopie.

 Operace get A získání přináší uživatele pracovní kopie aktuální kopii úložiště. Na rozdíl od checkout get provést, pokud se uživatel jednoduše potřebuje nejnovější ale si klade za cíl neprovádějte žádné změny.

 Historie je obvykle souhrn všech rezervace, vrácení se změnami, aktualizace, značky a verzí v úložišti správy zdrojů.

 Integrované vývojové prostředí obvykle odkazuje na Visual Studio integrované vývojové prostředí. Ale může také odkazovat na jiné prostředí klienta, které rozhraní API modulu Plug-in zdroje ovládacího prvku.

 Sloučit procesu, během kterého nejmíň dva zdroje jsou soubory kódu se spojí dohromady a tvoří nový soubor, který zahrnuje všechny funkce z předchozí soubory. Tento koncept je důležité ve správě verzí místo, kde dva nebo více vývojáři pracovat na souborech současně.

 Složka správy zdrojového kódu A projekt se často označuje jako projekt. To nemá žádný vztah s projekty nebo řešení v sadě Visual Studio.

 Modul plug-in knihovnu DLL, která poskytuje funkce správy zdrojového kódu pomocí implementace rozhraní API modulu Plug-in zdroje ovládacího prvku.

 Úložiště hlavní kopie, kde systém správy zdrojového kódu uchovává historii kompletní revizi projektu. Každý projekt má přesně jedno úložiště.

 Revize A potvrzené změny v historii souboru nebo sady souborů. Revizi patří pořízení snímku v neustále se měnící projektu.

## <a name="see-also"></a>Viz také
- [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)