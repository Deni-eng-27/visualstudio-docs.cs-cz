---
title: Upravit a pokračovat není podporována pro F# | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue [F#]
- Debugging [F#], Edit and Continue
ms.assetid: 40ec77bb-07e3-4b58-9254-ae015009441c
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a4fef61335679e3f82d5916726981e003bf9c332
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54803320"
---
# <a name="edit-and-continue-not-supported-for-f"></a>Operace Upravit a pokračovat není podporována pro F#. #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Upravit a pokračovat není podporovaná při ladění F# kódu. Úpravy F# kódu je možné během relace ladění, ale mělo by se vyhnout. Během relace ladění se nepoužijí změny kódu. Proto se veškeré úpravy provedené F# kódu během ladění způsobí zdrojový kód, který neodpovídá kódu, který se právě ladí.
