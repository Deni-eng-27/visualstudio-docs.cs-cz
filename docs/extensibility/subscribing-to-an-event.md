---
title: Přihlášení k odběru události | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- running document table (RDT), responding to events
- running document table (RDT), subscribing to events
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5dbb3c9db722ff335fd8dddadfffed57457d23ef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916923"
---
# <a name="subscribing-to-an-event"></a>Přihlášení k odběru události
Tento návod popisuje, jak vytvořit okno nástroje, který reaguje na události v tabulce spuštěných dokumentů (r...). Panel nástrojů hostuje uživatelský ovládací prvek, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> Metoda rozhraní se připojí k události.  
  
## <a name="prerequisites"></a>Požadavky  
 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="subscribing-to-rdt-events"></a>Přihlášení k odběru událostí r...  
  
#### <a name="to-create-an-extension-with-a-tool-window"></a>Vytváření rozšíření pomocí panelu nástrojů  
  
1.  Vytvoření projektu s názvem **RDTExplorer** VSIX šablony a přidat šablonu vlastního nástroje okna položku s názvem **RDTExplorerWindow**.  
  
     Další informace o vytváření rozšíření pomocí panelu nástrojů najdete v tématu [vytváření rozšíření pomocí panelu nástrojů](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
#### <a name="to-subscribe-to-rdt-events"></a>Přihlásit k odběru události r...  
  
1.  Otevřete soubor RDTExplorerWindowControl.xaml a tlačítko s názvem odstranit `button1`. Přidat <xref:System.Windows.Forms.ListBox> řídit a přijměte výchozí název. Element mřížky by měl vypadat nějak takto:  
  
    ```xml  
    <Grid>  
        <StackPanel Orientation="Vertical" Margin="-10,10,10,0">  
            <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock>  
            <ListBox x:Name="listBox" Height="100" />  
        </StackPanel>  
    </Grid>  
    ```  
  
2.  Otevřete soubor RDTExplorerWindow.cs v zobrazení kódu. Přidejte následující příkazy using do začátku souboru.  
  
    ```csharp  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  Upravit `RDTExplorerWindow` třídy tak, že kromě odvozený od <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> třída implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> rozhraní.  
  
    ```csharp  
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents  
    {. . .}  
    ```  
  
4.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>.  
  
    -   Implementujte rozhraní. Umístěte kurzor na název IVsRunningDocTableEvents. Měli byste vidět návrhy na levém okraji. Klikněte na šipku dolů napravo od žárovky a vyberte **implementovat rozhraní**.  
  
5.  V každé metodě v rozhraní, nahraďte řádek `throw new NotImplementedException();` s tímto:  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
6.  Přidejte pole souboru cookie RDTExplorerWindow třídy.  
  
    ```csharp  
    private uint rdtCookie;   
    ```  
  
     To obsahuje souboru cookie, který je vrácený <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> metody.  
  
7.  Přepište metodu Initialize() RDTExplorerWindow společnosti k registraci pro r... události. Vždy byste měli získat služby v metodu třídy ToolWindowPane Initialize(), není v konstruktoru.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
        this.GetService(typeof(SVsRunningDocumentTable));  
        rdt.AdviseRunningDocTableEvents(this, out rdtCookie);  
    }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> Služby je volána k získání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> Metoda připojí rámcový události na objekt, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>, v tomto případě RDTExplorer objektu.  
  
8.  Metoda Dispose() RDTExplorerWindow aktualizace.  
  
    ```csharp  
    protected override void Dispose(bool disposing)  
    {  
        // Release the RDT cookie.  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
            Package.GetGlobalService(typeof(SVsRunningDocumentTable));  
        rdt.UnadviseRunningDocTableEvents(rdtCookie);  
  
        base.Dispose(disposing);  
    }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnadviseRunningDocTableEvents%2A> Metoda odstraní spojení mezi `RDTExplorer` a r... oznámení události.  
  
9. Přidejte následující řádek do těla <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> obslužnou rutinu, těsně před `return` příkazu.  
  
    ```csharp  
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
10. Přidat řádek podobný do těla <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterFirstDocumentLock%2A> obslužná rutina a další události, které chcete zobrazit v rozevíracím seznamu.  
  
    ```csharp  
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
11. Sestavte projekt a spusťte ladění. Experimentální instanci sady Visual Studio se zobrazí.  
  
12. Otevřít **RDTExplorerWindow** (**zobrazení nebo jiných Windows / RDTExplorerWindow**).  
  
     **RDTExplorerWindow** otevře se okno se seznamem prázdný události.  
  
13. Otevřete nebo vytvořte řešení.  
  
     Jako `OnBeforeLastDocument` a `OnAfterFirstDocument` jsou vyvolávány události, oznámení událostí událostí se zobrazí v seznamu.