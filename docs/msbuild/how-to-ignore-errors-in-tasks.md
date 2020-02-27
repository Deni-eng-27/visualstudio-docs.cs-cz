---
title: 'Postupy: ignorování chyb v úlohách | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
author: ghogen
ms.author: ghogen
manager: jillfra
ms.openlocfilehash: 9899b7367e6ae9255755ae04fe06d8c8733043ae
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77633821"
---
# <a name="how-to-ignore-errors-in-tasks"></a>Postupy: ignorování chyb v úlohách

Někdy je vhodné, aby bylo sestavení odolné vůči chybám v určitých úlohách. Pokud tyto nekritické úkoly selžou, chcete, aby sestavení pokračovalo, protože stále může vytvořit požadovaný výstup. Například pokud projekt používá úlohu `SendMail` k odeslání e-mailové zprávy po sestavení každé součásti, může být vhodné, aby sestavení bylo přijatelné i v případě, že poštovní servery nejsou k dispozici a nelze odeslat stavové zprávy. Nebo například pokud jsou během sestavení obvykle smazány mezilehlé soubory, může být vhodné, aby sestavení bylo přijatelné i v případě, že tyto soubory nelze odstranit.

## <a name="use-the-continueonerror-attribute"></a>Použití atributu ContinueOnError

Atribut `ContinueOnError` elementu `Task` určuje, zda je sestavení zastaveno nebo pokračuje, když dojde k selhání úlohy. Tento atribut také určuje, zda jsou chyby považovány za chyby nebo upozornění, když sestavení pokračuje.

Atribut `ContinueOnError` může obsahovat jednu z následujících hodnot:

- **WarnAndContinue** nebo **true**. Pokud se úloha nezdařila, následné úkoly v [cílovém](../msbuild/target-element-msbuild.md) elementu a sestavení se budou dále spouštět a všechny chyby z tohoto úkolu jsou považovány za upozornění.

- **ErrorAndContinue**. Pokud se úloha nezdařila, následné úkoly v prvku `Target` a sestavení se budou dále spouštět a všechny chyby z tohoto úkolu jsou považovány za chyby.

- **ErrorAndStop** nebo **false** (výchozí). Pokud se úloha nezdařila, zbývající úkoly v prvku `Target` a sestavení nejsou provedeny a celý `Target` element a sestavení se považuje za neúspěšné.

Verze .NET Framework před 4,5 podporují pouze hodnoty `true` a `false`.

Výchozí hodnota `ContinueOnError` je `ErrorAndStop`. Pokud nastavíte atribut na `ErrorAndStop`, uděláte chování explicitně pro kohokoli, kdo soubor projektu přečte.

#### <a name="to-ignore-an-error-in-a-task"></a>Ignorování chyby v úloze

Použijte atribut `ContinueOnError` úlohy. Příklad:

```xml
<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>
```

## <a name="example"></a>Příklad

Následující příklad kódu ukazuje, že cílový `Build` stále běží a sestavení je považováno za úspěšné, i když se úloha `Delete` nezdařila.

```xml
<Project DefaultTargets="FakeBuild"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <ItemGroup>
        <Files Include="*.obj"/>
    </ItemGroup>
    <Target Name="Clean">
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>
    </Target>

    <Target Name="FakeBuild" DependsOnTargets="Clean">
        <Message Text="Building after cleaning..."/>
    </Target>
</Project>
```

## <a name="see-also"></a>Viz také

- [MSBuild](../msbuild/msbuild.md)
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
- [Úlohy](../msbuild/msbuild-tasks.md)
