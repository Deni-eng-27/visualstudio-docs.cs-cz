---
title: ShowWebBrowser – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a46f37f93340226c669df5db59745af17c7b2464
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958885"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser – příkaz

Zobrazí adresu URL zadanou v okně webového prohlížeče buď v rámci integrovaného vývojového prostředí (IDE) nebo mimo prostředí IDE.

## <a name="syntax"></a>Syntaxe

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
 `URL`

 Povinný parametr. Adresa URL (Uniform Resource Locator) pro web.

## <a name="switches"></a>Přepínače
 / Nový

 Volitelné. Určuje, že se zobrazí v nové instanci webového prohlížeče.

 /ext

 Volitelné. Určuje, že se zobrazí ve webovém prohlížeči výchozí mimo rozhraní IDE.

## <a name="remarks"></a>Poznámky
 Alias **showwebbrowser –** příkaz je **přejděte** nebo **nav**.

## <a name="example"></a>Příklad
 Následující příklad zobrazí domovská stránka Microsoft Docs ve webovém prohlížeči mimo rozhraní IDE. Pokud instance webového prohlížeče je už otevřená, je použit. v opačném případě se spustí novou instanci.

```cmd
>View.ShowWebBrowser https://docs.microsoft.com /ext
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)