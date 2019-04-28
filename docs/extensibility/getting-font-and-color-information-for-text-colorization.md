---
title: Písma a barvy informace pro barevné zvýraznění textu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text, coloring
- font and color control [Visual Studio SDK], coloring
ms.assetid: d1f985bd-743e-40b7-9458-d9af53647c91
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8f03b23076b1eea203166bb0322f05927480a278
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63417161"
---
# <a name="get-font-and-color-information-for-text-colorization"></a>Získání informací o písma a barvy pro barevné zvýraznění textu
Proces, který vykreslí nebo barevně zvýrazněné text se zobrazí prvky uživatelského rozhraní (UI) závisí na typu projektu, technologie a developer předvolby. **Písma a barvy** stránku vlastností ukládá nastavení.

 Většina implementací, které se zobrazí text barevně zvýrazněné potřebují <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> a přidružené rozhraní pro nastavení zobrazení prezentace, načítání a ukládání textu.

> [!NOTE]
> Při přizpůsobování základní editor (která podporuje **Text EditorCategory**), se doporučuje použít technologii barevné zvýraznění ve službě jazyka. Další informace najdete v tématu [přehled písma a barvy](../extensibility/font-and-color-overview.md).

## <a name="get-default-font-and-color-information"></a>Získání informací o výchozí písmo a barvy
 Všechny **písma a barvy** nastavení jakékoli okno zobrazení textu musí být zadán v **zobrazit položky** jednoho **kategorie**. Další informace najdete v tématu [písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md).

Barevně zvýrazňovat, musíte získat VSPackage aktuální **písma a barvy** nastavení. VSPackage můžete získat aktuální nastavení následujícími způsoby v závislosti na svých potřeb:

- Pomocí mechanismu trvalosti písma a barvy uložené nebo aktuální stav. Další informace najdete v tématu [přístup uložená nastavení písem a barev](../extensibility/accessing-stored-font-and-color-settings.md).

- Použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> rozhraní služby, který poskytuje data písma a barvy pro získání instance <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>, nejsou-li sady VSPackage také poskytovatele písmo a barvu.

- Implementujte rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>.

Chcete-li zajistit, aby získala při dotazování na výsledky jsou aktuální, může být vhodné použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> rozhraní k určení, zda aktualizace je nutné před voláním metody načítání <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní.

Poté co získané informace písma a barvy, analyzovat text, který má být zobrazen za účelem identifikování prvky, které vyžadují zabarvení. Zobrazení textu v okně pomocí odpovídající písma a barvy.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>
- [Použití písem a textu](/dotnet/framework/winforms/advanced/using-fonts-and-text)
- [Práce s barvou](/cpp/windows/working-with-color-image-editor-for-icons)
- [Rozhraní GDI (graphics zařízení rozhraní)](https://msdn.microsoft.com/library/7e1d4540-bb2e-4257-8eee-eee376acba83)