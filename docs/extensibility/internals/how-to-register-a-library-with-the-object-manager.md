---
title: "Postupy: registrace pomocí správce objekt knihovny | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- libraries, registering with object manager
- IVsLibrary2 interface, registering library with object manager
- IVsSimpleLibrary2 interface, registering library with object manager
- IVsObjectManager2 interface, registering library with object manager
- libraries, symbol-browsing tools
ms.assetid: f124dd05-cb0f-44ad-bb2a-7c0b34ef4038
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4ecb20a39657fd9a1e668321654dd2a293807adf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-a-library-with-the-object-manager"></a>Postupy: registrace knihovny pomocí Správce objektu
Procházení symboly nástrojů, jako je například **zobrazení tříd**, **Prohlížeč objektů**, **volání prohlížeče** a **Najít výsledky Symbol**, vám umožní zobrazit symboly v projektu nebo v externích součástí. Symboly zahrnují obory názvů, třídy, rozhraní, metod a další elementy jazyka. Sledování těchto symbolů do knihoven a umístěte je do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] správce objektů, které naplňuje nástroje s daty.  
  
 Objekt správce uchovává informace o dostupných knihoven. Každé knihovny, musíte zaregistrovat u správce objektu před poskytování symboly pro nástroje procházení symbol.  
  
 Až se načte VSPackage se obvykle zaregistrovat knihovnu. Nicméně je možné ji provést později podle potřeby. Při vypnutí VSPackage můžete zrušit registraci knihovny.  
  
 Chcete-li zaregistrovat knihovnu, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterLibrary%2A> metoda. V případě spravovaného kódu knihovny, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> metoda.  
  
 Chcete-li zrušit registraci knihovny, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> metoda.  
  
 Získat odkaz na objekt manager, <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, předat <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> služby ID `GetService` metoda.  
  
## <a name="registering-and-unregistering-a-library-with-the-object-manager"></a>Registrace a zrušení registrace knihovny pomocí Správce objektu  
  
#### <a name="to-register-a-library-with-the-object-manager"></a>Při registraci knihovny s Správce objektu  
  
1.  Vytvoření knihovny.  
  
    ```vb  
    Private m_CallBrowserLibrary As CallBrowser.Library = Nothing  
    Private m_nLibraryCookie As UInteger = 0  
    ' Create Library.  
    m_CallBrowserLibrary = New CallBrowser.Library()  
    ```  
  
    ```csharp  
    private CallBrowser.Library m_CallBrowserLibrary = null;  
    private uint m_nLibraryCookie = 0;  
    // Create Library.  
    m_CallBrowserLibrary = new CallBrowser.Library();  
  
    ```  
  
2.  Získat odkaz na objekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> zadejte a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> metoda.  
  
    ```vb  
    Private Sub RegisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            Throw New Exception("Library already registered with Object Manager")  
        End If  
  
        ' Obtain a reference to IVsObjectManager2 type object.  
        Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
        If objManager Is Nothing Then  
            Throw New NullReferenceException("GetService failed for SVsObjectManager")  
        End If  
  
        Try  
            Dim hr As Integer = objManager.RegisterSimpleLibrary(m_CallBrowserLibrary, m_nLibraryCookie)  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr)  
        Catch e As Exception  
            ' Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message)  
            Throw  
        End Try  
    End Sub  
    ```  
  
    ```csharp  
    private void RegisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
            throw new Exception("Library already registered with Object Manager");  
  
        // Obtain a reference to IVsObjectManager2 type object.  
        IVsObjectManager2 objManager =   
                          GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
        if (objManager == null)  
            throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
        try  
        {  
            int hr =   
                objManager.RegisterSimpleLibrary(m_CallBrowserLibrary,   
                                                 out m_nLibraryCookie);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
        }  
        catch (Exception e)  
        {  
            // Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message);  
            throw;  
        }  
    }  
  
    ```  
  
#### <a name="to-unregister-a-library-with-the-object-manager"></a>Zrušit registraci knihovny pomocí Správce objektu  
  
1.  Získat odkaz na objekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> zadejte a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> metoda.  
  
    ```vb  
    Private Sub UnregisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            ' Obtain a reference to IVsObjectManager2 type object.  
            Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
            If objManager Is Nothing Then  
                Throw New NullReferenceException("GetService failed for SVsObjectManager")  
            End If  
  
            Try  
                objManager.UnregisterLibrary(m_nLibraryCookie)  
            Catch e As Exception  
                ' Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message)  
                Throw  
            Finally  
                m_nLibraryCookie = 0  
            End Try  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void UnregisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
        {  
            // Obtain a reference to IVsObjectManager2 type object.  
            IVsObjectManager2 objManager = GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
            if (objManager == null)  
                throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
            try  
            {  
                objManager.UnregisterLibrary(m_nLibraryCookie);  
            }  
            catch (Exception e)  
            {  
                // Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message);  
                throw;  
            }  
            finally  
            {  
                m_nLibraryCookie = 0;  
            }  
        }  
    }  
  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření služby starší verze jazyka](../../extensibility/internals/legacy-language-service-extensibility.md)   
 [Podpůrné nástroje procházení – Symbol](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Postupy: Zveřejnění seznamů symbolů poskytovaných knihovnou správci objektů](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)