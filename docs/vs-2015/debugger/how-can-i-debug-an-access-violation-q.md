---
title: Jak mohu ladit narušení přístupu? | Dokumenty Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 073fc84d15cb31b4f7a4cc635524ab08a724911e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68147849"
---
# <a name="how-can-i-debug-an-access-violation"></a>Jak mohu ladit narušení přístupu?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popis problému  
 Tento program vytvoří narušení přístupu. Jak to lze odladit?  
  
## <a name="solution"></a>Řešení  
 Pokud dojde k narušení přístupu na řádek kódu, který přistoupí přes většího počtu ukazatelů, může být obtížné zjistit, které ukazatel způsobil narušení přístupu. Od verze Visual Studio 2015 Update 1, dialogové okno výjimky nyní explicitně názvy ukazatel, který způsobil narušení přístupu.  
  
 Například směru následujícím kódem, měli byste získat narušení přístupu:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ClassB {  
public:  
      ClassC* C;  
      ClassB() {  
            C = new ClassC();  
      }  
     void printHello() {  
            cout << "hello world";  
      }  
};  
  
class ClassA {  
public:  
    ClassB* B;  
    ClassA() {  
            B = nullptr;  
      }  
};  
  
int main() {  
    ClassA* A = new ClassA();  
    A->B->printHello();  
}  
```  
  
 Při spuštění tohoto kódu ve Visual Studio 2015 Update 1, byste měli vidět následující dialogové okno výjimky:  
  
 ![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
 Pokud nelze určit, proč je ukazatel způsobil narušení přístupu, trasování skrze kód a ujistěte se, že ukazatel příčinou problému, má přiřazenou správně.  Pokud je předán jako parametr, ujistěte, že je jí předán správně, a nejsou omylem vytváření [Nedávná kopírování](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy). Ověřte, že hodnoty nejsou mění neúmyslně někde v programu vytvořením datové zarážky pro ukazatele dotyčný zajistit, aby že se nemění jinde v programu. Další informace o datové zarážky, najdete v části zarážky data v [pomocí zarážek](../debugger/using-breakpoints.md).  
  
## <a name="see-also"></a>Viz také  
 [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
