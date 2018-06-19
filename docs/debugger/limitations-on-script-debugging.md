---
title: Omezení ladění skriptů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASPX breakpoint mapping, limitations
- script debugging, limitations
- breakpoint mapping, limitations
ms.assetid: 280eead5-693c-47af-967f-dfe9d23f84db
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6679e781e564a58d6a98b7d0190f2f2b4e9fa74
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476832"
---
# <a name="limitations-on-script-debugging"></a>Omezení ladění skriptů
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podporuje ladění skriptů na straně klienta, vztahují omezení v tomto tématu.  
  
## <a name="limitations-on-breakpoint-mapping-with-client-side-script"></a>Omezení mapování zarážek pomocí skriptu na straně klienta  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Umožňuje nastavit zarážky v souboru serverové ASPX nebo HTML, který převede do souboru na straně klienta za běhu. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mapuje zarážek ze souboru na straně serveru pro odpovídající zarážky v souboru na straně klienta, vztahují následující omezení:  
  
-   Musí být nastavena zarážky uvnitř `<script>` bloky. Zarážky v vloženého skriptu nebo `<% %>` bloky nemůže být namapovaný.  
  
-   V prohlížeči adresu URL stránky musí obsahovat název stránky. Například http://microsoft.com/default.apsx. Mapování zarážek nemůže rozpoznat jako přesměrování z adresy http://microsoft.com na výchozí stránku.  
  
-   Zarážce musí být nastavena na stránce zadaného v adrese URL prohlížeče, není v souboru ASPX ovládací prvek (ascx), hlavní stránky nebo jiný soubor v této stránce zahrnuty. Nelze mapovat zarážky nastavit zahrnuté stránkách.  
  
-   Nastavte zarážky v `<script defer=true>` nelze mapovat bloky.  
  
-   Pro nastavte zarážky v `<script id="">` bloky, ignoruje mapování zarážek `id` atribut.  
  
## <a name="breakpoint-mapping-and-duplicate-lines"></a>Mapování zarážek a duplicitní řádky  
 Algoritmus mapování zarážek a vyhledejte odpovídající umístění ve skriptu na straně serveru a na straně klienta, prověří kód na každém řádku. Algoritmus předpokládá, že každý řádek je jedinečný. Pokud dva nebo více řádků obsahovat stejný kód, a nastavte zarážky v jednom z těchto duplicitní řádky, může algoritmus mapování zarážek vyberte nesprávný duplicitní v souboru na straně klienta. Chcete-li tomu zabránit, přidejte komentář k řádku, kde jste nastavili zarážku. Příklad:  
  
```  
i++ ;  
i ++; // I added a comment, so this line is now unique  
i ++;  
```