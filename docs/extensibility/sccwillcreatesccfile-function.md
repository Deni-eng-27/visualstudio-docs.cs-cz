---
title: Funkce SccWillCreateSccFile | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccWillCreateSccFile
helpviewer_keywords:
- SccWillCreateSccFile function
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0694fd6b4ba82faf8b05354765fc5734efe2ef4d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700200"
---
# <a name="sccwillcreatesccfile-function"></a>SccWillCreateSccFile – funkce
Tato funkce určuje, zda modul plug-in správy zdrojových kódů podporuje vytváření MSSCCPRJ. SCC soubor pro každý z daných souborů.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccWillCreateSccFile(
   LPVOID  pContext,
   LONG    nFiles,
   LPCSTR* lpFileNames,
   LPBOOL  pbSccFiles
);
```

#### <a name="parameters"></a>Parametry
 pContext

pro Ukazatel kontextu modulu plug-in správy zdrojových kódů.

 nFiles

pro Počet názvů souborů obsažených v `lpFileNames` poli a také délka `pbSccFiles` pole.

 lpFileNames

pro Pole plně kvalifikovaných názvů souborů k ověření (pole musí být přiděleno volajícím).

 pbSccFiles

[in, out] Pole, do kterého mají být uloženy výsledky.

## <a name="return-value"></a>Návratová hodnota
 Při implementaci modulu plug-in správy zdrojových kódů této funkce se očekává, že se vrátí jedna z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Úspěch.|
|SCC_E_INVALIDFILEPATH|Jedna z cest v poli je neplatná.|
|SCC_E_NONSPECIFICERROR|Nespecifická chyba.|

## <a name="remarks"></a>Poznámky
 Tato funkce se volá se seznamem souborů, abyste zjistili, jestli modul plug-in správy zdrojových kódů poskytuje podporu v MSSCCPRJ. SCC soubor pro každý z daných souborů (Další informace najdete v MSSCCPRJ. Soubor SCC, viz [MSSCCPRJ. Soubor SCC](../extensibility/mssccprj-scc-file.md)). Moduly plug-in správy zdrojových kódů můžou deklarovat, jestli mají schopnost vytvářet MSSCCPRJ. SCC soubory deklarací `SCC_CAP_SCCFILE` při inicializaci. Modul plug-in vrátí `TRUE` nebo `FALSE` na soubor v `pbSccFiles` poli a určí, který z daných souborů má MSSCCPRJ. Podpora SCC Pokud modul plug-in vrátí kód úspěchu z funkce, jsou dodrženy hodnoty v poli Return. Při selhání se pole ignoruje.

## <a name="see-also"></a>Viz také
- [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
- [Soubor MSSCCPRJ.SCC](../extensibility/mssccprj-scc-file.md)
