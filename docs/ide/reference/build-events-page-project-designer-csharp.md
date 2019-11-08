---
title: Stránka Události sestavení, návrhář projektu (C#)
ms.date: 10/17/2019
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4842a5a08de96cd40a45d0765d427cc74cbf5432
ms.sourcegitcommit: ba0fef4f5dca576104db9a5b702670a54a0fcced
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2019
ms.locfileid: "73714391"
---
# <a name="build-events-page-project-designer-c"></a>Stránka Události sestavení, návrhář projektu (C#)

Pomocí stránky **události sestavení** **Návrháře projektu** můžete zadat pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých budou spouštěny události po sestavení. Další informace naleznete v tématu [How to: zadat události sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md) a [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Konfigurace**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

**Platformy**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

**Příkazový řádek události před sestavením**

Určuje, které příkazy se mají provést před zahájením sestavení. Chcete-li zadat dlouhé příkazy, klikněte na tlačítko **Upravit před sestavením** a zobrazte tak [dialogové okno Příkazový řádek události před sestavením/po sestavení](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Události před sestavením se nespustí, pokud je projekt aktuální a není spuštěno žádné sestavení.

**Příkazový řádek události po sestavení**

Určuje všechny příkazy, které mají být provedeny po ukončení sestavení. Chcete-li zadat dlouhé příkazy, klikněte na **Upravit po sestavení** , aby se zobrazilo **dialogové okno Příkazový řádek události před sestavením/po sestavení**.

> [!NOTE]
> Přidejte příkaz `call` před všechny příkazy po sestavení, které spouštějí soubory. bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.

**Spustit událost po sestavení**

Určuje následující podmínky pro spuštění události po sestavení, jak je znázorněno v následující tabulce.

|Možnost|Výsledek|
|------------|------------|
|**Stál**|Událost po sestavení se spustí bez ohledu na to, jestli je sestavení úspěšné.|
|**Po úspěšném sestavení**|Událost po sestavení se spustí, pokud je sestavení úspěšné. Proto se událost spustí i pro projekt, který je aktuální, pokud je sestavení úspěšné.|
|**Když sestavení aktualizuje výstup projektu**|Událost po sestavení se spustí pouze v případě, že výstupní soubor kompilátoru (. exe nebo. dll) je jiný než předchozí výstupní soubor kompilátoru. Proto se událost po sestavení nespustí, pokud je projekt aktuální.|

## <a name="in-the-project-file"></a>V souboru projektu

V dřívějších verzích sady Visual Studio, pokud změníte nastavení **PreBuildEvent** nebo **PostBuildEvent** v rozhraní IDE, Visual Studio přidá do souboru projektu vlastnost `PreBuildEvent` nebo `PostBuildEvent`. Například pokud vaše nastavení příkazového řádku **PreBuildEvent** v integrovaném vývojovém prostředí je následující:

```input
"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"
```

nastavení soubor projektu je:

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

Pro projekty .NET Core Visual Studio 2019 (a Visual Studio 2017 v novějších aktualizacích) přidá cíl MSBuild s názvem `PreBuild` nebo `PostBuild` pro nastavení **PreBuildEvent** a **PostBuildEvent** . Tyto cíle používají atributy **BeforeTargets** a **AfterTargets** , které nástroj MSBuild rozpozná. Například pro předchozí příklad nyní Visual Studio generuje následující kód:

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>
```

Pro událost po sestavení použijte název `PostBuild` a nastavte atribut `AfterTargets` na `PostBuildEvent`.

```xml
<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
> Tyto změny souborů projektu byly provedeny pro podporu projektů ve stylu sady SDK. Pokud migrujete soubor projektu z původního formátu do formátu sady SDK ručně, měli byste odstranit `PreBuildEvent` a `PostBuildEvent` vlastnosti a nahradit je `PreBuild` a `PostBuild` cíle, jak je uvedeno v předchozím kódu. Informace o tom, jak zjistit, zda se jedná o projekt ve stylu sady SDK, naleznete v tématu [check Project Format](/nuget/resources/check-project-format).

## <a name="see-also"></a>Viz také:

- [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Postupy: Specifikace událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)
- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)