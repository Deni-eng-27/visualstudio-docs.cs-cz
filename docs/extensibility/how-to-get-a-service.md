---
title: 'Postupy: Získání služby | Dokumentace Microsoftu'
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- services, consuming
ms.assetid: 1f000020-8fb7-4e39-8e1e-2e38c7fec3d4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 027057ff5c6f8d33038329a8e6029dcb4eeac477
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194305"
---
# <a name="how-to-get-a-service"></a>Postupy: Získání služby

Často je potřeba získat služby Visual Studio pro přístup k jiné funkce. Obecně platí služby Visual Studio obsahuje jedno nebo více rozhraní, které můžete použít. Většina služeb můžete získat z VSPackage.

Žádné VSPackage, která je odvozena z <xref:Microsoft.VisualStudio.Shell.Package> a který správně umístěný požádat o žádné globální služby. Protože `Package` implementuje třída <xref:System.IServiceProvider>, všechny VSPackage, která je odvozena z `Package` je také poskytovatele služeb.

Načtení sady Visual Studio <xref:Microsoft.VisualStudio.Shell.Package>, předá <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> metoda během inicializace. Tento postup se nazývá *umístění* sady VSPackage. `Package` Třída zabalí tuto poskytovatele služeb a poskytuje <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metody pro získání služby.

## <a name="getting-a-service-from-an-initialized-vspackage"></a>Získání služby z inicializované VSPackage

1. Každé rozšíření sady Visual Studio spustí nasazení projektu VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projekt s názvem `GetServiceExtension`. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Nyní přidejte vlastní příkaz šablonu položky s názvem **GetServiceCommand**. V **přidat novou položku** dialogové okno, přejděte na **Visual C#** > **rozšiřitelnost** a vyberte **vlastního příkazu**. V **název** pole v dolní části okna, změňte název souboru příkazu *GetServiceCommand.cs*. Další informace o tom, jak vytvořit vlastní příkaz [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)

3. V *GetServiceCommand.cs*, odeberte text `MenuItemCommand` metoda a přidejte následující kód:

   ```csharp
   IVsActivityLog activityLog = ServiceProvider.GetService(typeof(SVsActivityLog)) as IVsActivityLog;
   if (activityLog == null) return;
   System.Windows.Forms.MessageBox.Show("Found the activity log service.");

   ```

    Tento kód získá služby SVsActivityLog a přetypování na <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní, které lze použít k zápisu do protokolu aktivit. Příklad najdete v tématu [jak: Použití protokolu aktivit](../extensibility/how-to-use-the-activity-log.md).

4. Sestavte projekt a spusťte ladění. Zobrazí se experimentální instance.

5. Na **nástroje** nabídky experimentální instanci najdete **vyvolat GetServiceCommand** tlačítko. Po kliknutí na toto tlačítko, zobrazí se okno se zprávou, že **najít službu protokolu aktivit.**

## <a name="getting-a-service-from-a-tool-window-or-control-container"></a>Získání služby z nástroje okna nebo ovládací prvek kontejneru

V některých případech budete muset získat službu z panelu nástrojů nebo ovládací prvek kontejneru, který nebyl byl umístěn, jinak byl umístěn u poskytovatele služeb, které neví o službu, kterou chcete. Můžete například chtít zapisovat do protokolu aktivit z v rámci ovládacího prvku.

Statické <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda závisí na zprostředkovateli služby uložený v mezipaměti, který je inicializován poprvé jakékoli VSPackage odvozený od <xref:Microsoft.VisualStudio.Shell.Package> je umístěn.

Protože VSPackage konstruktoru je volán předtím, než je umístěn sady VSPackage, jsou obvykle nedostupná z v rámci konstruktoru VSPackage služeb global services. Zobrazit [jak: Odstraňování potíží se službami](../extensibility/how-to-troubleshoot-services.md) alternativní řešení.

Tady je příklad toho, jak se získat službu v panelu nástrojů nebo jiného elementu bez VSPackage.

```csharp
IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
if (log == null) return;
```

## <a name="getting-a-service-from-the-dte-object"></a>Získání služby z objektu DTE

Můžete také získat služby od <xref:EnvDTE.DTEClass> objektu. Ale musíte získat objekt DTE jako služba z VSPackage nebo voláním statické <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metody.

Implementuje objekt DTE <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, který můžete použít k dotazování služby s použitím <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>.

Tady je postup, chcete-li získat službu z objektu DTE.

```csharp
// Start with the DTE object, for example: 
// using EnvDTE;
// DTE dte = (DTE)GetService(typeof(DTE));

ServiceProvider sp = new ServiceProvider((Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);
if (sp != null)
{
    IVsActivityLog log = sp.GetService(typeof(SVsActivityLog)) as IVsActivityLog;
    if (log != null)
    {
        System.Windows.Forms.MessageBox.Show("Found the activity log service.");
    }
}
```

## <a name="see-also"></a>Viz také:

- [Postupy: Poskytování služeb](../extensibility/how-to-provide-a-service.md)
- [Použít a poskytování služeb](../extensibility/using-and-providing-services.md)
- [Základy služby](../extensibility/internals/service-essentials.md)