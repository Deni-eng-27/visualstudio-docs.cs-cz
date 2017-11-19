---
title: "Podmíněné atributy schématu VSCT XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b0a434800fef7029460854107e79f29a71c75285
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsct-xml-schema-conditional-attributes"></a>Podmíněné atributy schématu VSCT XML
Podmíněné atributy může být použity na všechny seznamy a položky. Logické operátory a výrazy rozšíření symbol vyhodnotí jako true nebo false. V případě hodnoty true, jsou přidružený seznam nebo položka je součástí výsledný výstup.  
  
 Token rozšíření může být porovnávaný další token rozšiřuje nebo konstanty. Funkce Defined() se používá k ověření, zda byla definována konkrétní název, i když nemá žádnou hodnotu.  
  
 Stav atributu se použije k seznamu, podmínky platí pro každý podřízený element v seznamu. Pokud podřízený element samotné obsahuje atribut podmínku, pak jeho podmínky spolu s výraz nadřazené a operace.  
  
 Hodnoty 1, '1' a 'true', jsou vyhodnoceny jako true, a 0, "0", "Nepravda", jsou vyhodnoceny jako false.  
  
## <a name="operators"></a>Operátory  
 Následující operátory slouží k vyhodnocení podmíněné výrazy.  
  
|Operátor|Definice|  
|--------------|----------------|  
|(,)|Seskupování|  
|!|Logický operátor not|  
|\<, >, \<=, >=, ==, !=|Relační a rovnosti|  
|and|Boolean|  
|or|Boolean|  
  
## <a name="examples"></a>Příklady  
  
```  
<Menu Condition="Defined(DEBUG)" ...  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" ...  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu ...  
        </Menu>  
    </Menus>  
  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)