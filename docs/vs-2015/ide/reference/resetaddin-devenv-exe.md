---
title: -ResetAddin (devenv. exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9958e6e9a540dce1a405df8991780600b8f4a702
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665604"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Odebere příkazy a uživatelské rozhraní příkazu přidružené k zadanému doplňku.

## <a name="syntax"></a>Syntaxe

```
Devenv /ResetAddin AddIn
```

## <a name="arguments"></a>Arguments
 `AddIn` volitelné. Název příkazu doplňku.

## <a name="remarks"></a>Poznámky
 Ve výchozím nastavení je název příkazu doplňku roven *\<AddInSolutionName >* . Connect<em>. \<AddInSolutionName ></em>a zobrazí se v Connect.cs jako parametr `commandName` metody `Exec`. Název příkazu můžete také ověřit tak, že začnete zadávat název doplňku do okna příkazy v aplikaci Visual Studio a pomocí technologie IntelliSense vyplníte zbytek.

## <a name="example"></a>Příklad
 Následující příklad spustí aplikaci Visual Studio a zabrání spuštění doplňku `MyAddin` při spuštění.

```
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin
```

## <a name="see-also"></a>Viz také
 [Přizpůsobení nastavení vývoje v](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3) [přepínačích příkazového řádku devenv](../../ide/reference/devenv-command-line-switches.md) sady Visual Studio
