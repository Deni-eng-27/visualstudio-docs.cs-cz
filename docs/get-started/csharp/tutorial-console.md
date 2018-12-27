---
title: 'Kurz: Začínáme s C# konzolové aplikace'
description: Zjistěte, jak vytvořit konzolovou aplikaci C# v sadě Visual Studio, krok za krokem.
ms.custom: seodec18, get-started
ms.date: 12/12/2018
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 333eeb3f826663d979e1cec444ede7eda4b55b2a
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/18/2018
ms.locfileid: "53562214"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>Kurz: Začínáme s aplikaci konzoly C# v sadě Visual Studio

V tomto kurzu pro jazyk C#, budete používat Visual Studio k vytváření a spustíte aplikaci konzoly a prozkoumat některé funkce [sady Visual Studio integrované vývojové prostředí (IDE)](../visual-studio-ide.md) při uděláte.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Pokud chcete začít, vytvoříme C# projekt aplikace. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru *Kalkulačka*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>Přidat do pracovní skupiny (nepovinné)

Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** pracovního vytížení. Zjistěte, jak to udělat, najdete v článku "[co je zatížení a jak jeden přidat?](#workload)" části v části Nejčastější dotazy.

## <a name="create-the-app"></a>Vytvoření aplikace

Nejprve přidáme kód pro vytvoření základní kalkulačky. Dále jsme budete upravit kód pro přidání funkce. Potom jsme budeme ladit aplikaci vyhledat a opravit chyby. Nakonec jsme upřesníte kód, který efektivnější.

Začněme přidáním kódu základní kalkulačky k projektu.

1. V editoru kódu odstraňte výchozí kód "Hello World".

    ![Odstranit výchozí kódu Hello World z nové kalkulačky aplikace](./media/csharp-console-calculator-deletehelloworld.png)

   Konkrétně odstraňte veškerý kód, který se zobrazí v editoru kódu.

1. Zadejte nebo vložte následující nový kód do editoru kódu:

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```
1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

   ![Klikněte na tlačítko kalkulačky ke spuštění aplikace z panelu nástrojů](./media/csharp-console-calculator-button.png)

   Otevře se okno konzoly.

1. Zobrazení vaší aplikace v okně konzoly a postupujte podle pokynů pro přidání čísel **42** a **119**.

   Vaše aplikace by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Konzoly okno aplikace kalkulačky a zahrnuje dotazování na akce, které se má provést](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>Přidat desetinná místa

Kalkulačka aplikace nyní přijímá a vrací celá čísla. Ale bude přesnější, můžeme přidat kód, který umožňuje desetinná čísla.

Jako na následujícím snímku obrazovky Pokud spustíte aplikaci a rozdělit číslo 42 číslem 119, sady výsledků je 0 (nula), který není přesné.

![Okno konzoly zobrazující aplikaci kalkulačky, který nevrací desítkové číslice v důsledku](./media/csharp-console-calculator-nodecimal.png)

Opravíme kód tak, aby zpracovává desetinná čísla.

1. Změňte každou instanci `int` proměnnou `float`.

   (Můžete použít [najít a nahradit](../../ide/finding-and-replacing-text.md#find-and-replace-control) ovládacího prvku můžete s touto úlohou. Chcete-li získat přístup k vyhledávání ovládacího prvku v editoru kódu, stiskněte **Crtl**+**F**. Poté vyberte položku **najít další** tlačítko nebo **najít předchozí** tlačítka na ovládacím prvku hledání. Chcete-li přistupovat k možnostem výměny, klikněte na tlačítko vedle **najít** textového pole. Chcete-li nahrazovat po jednom čas, zvolte **nahradit další** vedle **nahradit** textového pole. Chcete-li nahradit všechny shody, zvolte **Nahradit vše** tlačítko.)

1. Znovu spusťte aplikaci kalkulačky a počet **42** číslem **119**.

   Všimněte si, že aplikace nyní vrací desítkových číslic namísto nula.

    ![Okna konzoly zobrazuje Kalkulačka aplikaci, která nyní vrací desetinná čísla v důsledku číslic.](./media/csharp-console-calculator-decimal.png)

Aplikace vytvoří však pouze desítkové výsledek. Vytvoříme několik další vylepšení kódu, tak, aby aplikace příliš vypočítat desetinná čísla.

1. Změňte každou instanci `float` proměnnou `double`.

1. Změňte každou instanci `Convert.ToInt32` metodu `Convert.ToDouble`.

1. Spusťte aplikaci kalkulačky a počet **42,5** číslem **119.75**.

   Všimněte si, že aplikace nyní přijímá desetinné hodnoty a jako svůj výsledek vrátí delší desítkových číslic.

    ![Okno konzoly Kalkulačka aplikace, které nyní přijímá desetinná čísla a vrátí delší desítkových číslic ve výsledku](./media/csharp-console-calculator-usedecimals.png)

    (Počet desetinných míst v opravíme [revizi kódu](#revise-the-code) části.)

## <a name="debug-the-app"></a>Ladění aplikace

Vylepšili jsme v naší aplikaci základní kalkulačky, ale ještě nemá failsafes v místě pro zpracování výjimek, jako jsou chyby vstupu uživatele.

Například, pokud se pokusíte dělení čísla nulou nebo zadejte alfanumerického znaku při aplikace očekává, že číselný znak (nebo naopak), aplikace přestane fungovat a vrátí chybu.

Pojďme si několik běžných chyby vstupu uživatele, vyhledejte je v [ladicí program](../../debugger/debugger-feature-tour.md)a opravte v kódu.

### <a name="fix-the-divide-by-zero-error"></a>Opravte chybu "dělení nulou"

Při pokusu o dělení čísla nulou se zablokuje konzolovou aplikaci. Visual Studio pak se dozvíte, co je špatně v editoru kódu.

   ![Editor kódu sady Visual Studio zobrazí chybu dělení nulou](./media/csharp-console-calculator-dividebyzero-error.png)

Změňme kód pro zpracování této chyby.

1. Odstranit kód, který se zobrazí přímo mezi `case "d":` a komentář, který říká `// Wait for the user to respond before closing`.

1. Nahraďte ho následujícím kódem:

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   Poté, co přidáte kód do oddílu `switch` příkaz by měl vypadat podobně jako na následujícím snímku obrazovky:

   ![V části revidované "přepínač" v editoru kódu sady Visual Studio](./media/csharp-console-calculator-switch-code.png)

Nyní po libovolný počet dělení nulou, aplikace bude požádat o jiné číslo. Dokonce lepší: Nezpůsobí ukončení, s dotazem, dokud nezadáte jiné číslo než nula.

   ![Editor kódu sady Visual Studio zobrazí chybu dělení nulou](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>Opravte chyba "formát"

Pokud zadáte alfanumerického znaku při aplikace očekává, že číselný znak (nebo naopak), zablokuje aplikace konzoly. Visual Studio pak se dozvíte, co je špatně v editoru kódu.

   ![Editor kódu sady Visual Studio se zobrazí chyba formátu](./media/csharp-console-calculator-format-error.png)

Chcete-li vyřešit tuto chybu, jsme musí Refaktorovat kód, který jste dříve zadali.

#### <a name="revise-the-code"></a>Revizi kódu

Místo využívají `program` třídy pro zpracování veškerý kód, naší aplikace budeme budete rozdělit do dvou tříd: `calculator` a `program`.  

`calculator` Třídy bude zpracovávat hromadné výpočtu práci a `program` třídy bude zpracovávat uživatelské rozhraní a zaznamenávání chyb práce.

Pusťme se do práce.

1. Vymazat úplně všechno *po* následující blok kódu:

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. V dalším kroku přidejte nový `calculator` třídy následujícím způsobem:

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. Pak přidejte novou `program` třídy následujícím způsobem:

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```
1. Zvolte **Kalkulačka** ke spuštění programu, nebo stiskněte klávesu **F5**.

1. Postupujte podle zobrazených výzev a počet **42** číslem **119**. Vaše aplikace by měl vypadat nějak takto:

    ![Okno konzoly refaktorovaný kalkulačky aplikaci, která zahrnuje výzvy, na které akcí a zpracování chyb pro nesprávný vstupy](./media/csharp-console-calculator-refactored.png)

    Všimněte si, že máte možnost zadat další rovnice, dokud nezavřete konzolovou aplikaci. A omezili jsme také počet desetinných míst ve výsledku.

## <a name="close-the-app"></a>Zavřete aplikaci

1. Pokud jste tak již neučinili, zavřete aplikaci kalkulačku.

1. Zavřít **výstup** podokno v sadě Visual Studio.

   ![Zavřete podokno výstup v sadě Visual Studio](./media/csharp-calculator-close-output-pane.png)

1. V sadě Visual Studio, stiskněte klávesu **Ctrl**+**S** a uložte aplikaci.

1. Zavřete Visual Studio.

## <a name="code-complete"></a>Kód je kompletní

Během této tutortial jsme spoustu změny do aplikace kalkulačku. Aplikace efektivněji nyní zpracovává výpočetní prostředky a zpracovává většinu chyby vstupu uživatele.

Tady je kompletní kód vše na jednom místě:

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="quick-answers-faq"></a>Rychlé odpovědi – nejčastější dotazy

Tady je rychlý – nejčastější dotazy ke zvýraznění některých klíčových koncepcí. V části Nejčastější dotazy také odpovědi na otázky, ke kterým může při postupujte podle pokynů v tomto kurzu.

### <a name="what-is-c"></a>Co je C#?

C# je programovací jazyk zajišťující bezpečnost typů, která běží na rozhraní .NET Framework a .NET Core. Pomocí jazyka C# můžete vytvořit Windows aplikace, klient-server, databázové aplikace, XML webové služby, distribuované součásti a další.

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

### <a name="what-is-a-console-app"></a>Co je konzolová aplikace?

Konzolová aplikace přijímá vstupní a zobrazí výstup v okně příkazového řádku, označovaný také jako do konzoly.

### <a name="what-is-net-core"></a>Co je .NET Core?

.NET core je dalším krokem evoluční rozhraní .NET Framework. Pokud rozhraní .NET Framework umožňují sdílení kódu napříč programovacími jazyky, .NET Core přidává možnost sdílení kódu napříč platformami. Ještě lepší je open source.

(Rozhraní .NET Framework a .NET Core zahrnují knihovny předem připravených funkce. Zahrnují taky, že common language runtime (CLR), který se chová jako virtuální počítač, ve kterém se spustí váš kód.)

### <a id="workload"></a>Co je zatížení a jak jeden přidat?

Úlohy v sadě Visual Studio představuje sadu programovací možnosti a šablony, které můžete použít k přizpůsobení instalace sady Visual Studio. Úloha se nainstaluje pouze těch nástrojů, které potřebujete pro programovací jazyk a platformu podle vašeho výběru. Tady je postup k instalaci.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt

1. Zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Zvolte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Pomocí nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Další ještě více, pokračujte v následujících kurzech.

> [!div class="nextstepaction"]
> [Výukové programy jazyka C#](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>Viz také:

* [Základy C# pro naprosté začátečníky videokurz](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)