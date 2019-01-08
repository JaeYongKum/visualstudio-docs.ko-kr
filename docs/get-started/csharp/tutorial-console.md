---
title: '자습서: C# 콘솔 앱 시작'
description: Visual Studio에서 C# 콘솔 앱을 만드는 방법을 단계별로 알아봅니다.
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
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53562219"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>자습서: Visual Studio에서 C# 콘솔 앱 시작

C#에 대한 이 자습서에서는 Visual Studio를 사용해서 콘솔 앱을 만들어 실행하고, 그 과정에서 [Visual Studio IDE(통합 개발 환경)](../visual-studio-ide.md)의 일부 기능을 살펴봅니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

시작하려면 C# 애플리케이션 프로젝트를 만듭니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 차례로 선택합니다.

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **C#** 을 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **콘솔 앱(.NET Core)** 을 선택합니다. 그런 다음, 파일 이름을 *Calculator*로 지정합니다.

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 콘솔 앱(.NET Core) 프로젝트 템플릿](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>(선택 사항) 작업 그룹 추가

**콘솔 앱(.NET Core)** 프로젝트 템플릿이 표시되지 않는 경우, **.NET Core 플랫폼 간 개발** 워크로드를 추가하여 얻을 수 있습니다. 이 작업을 수행하는 방법은 "[워크로드란 무엇이며 어떻게 추가하나요?](#workload)"를 참조하세요. FAQ의 섹션.

## <a name="create-the-app"></a>앱 만들기

먼저 기본 계산기를 만드는 코드를 추가합니다. 다음으로, 코드를 수정하여 기능을 추가하겠습니다. 그런 다음, 오류를 찾아 수정하기 위해 앱을 디버그할 것입니다. 마지막으로, 보다 효율적인 코드를 구체화하겠습니다.

기본 계산기 코드를 프로젝트에 추가하여 시작해 보겠습니다.

1. 코드 편집기에서 기본 "Hello World" 코드를 삭제합니다.

    ![새 계산기 앱에서 기본 Hello World 코드 삭제](./media/csharp-console-calculator-deletehelloworld.png)

   특히, 코드 편집기에 표시되는 모든 코드를 삭제합니다.

1. 코드 편집기에 다음 새 코드를 입력하거나 붙여넣습니다.

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
1. 프로그램을 실행할 **계산기**를 선택하거나 **F5** 키를 누릅니다.

   ![계산기 단추를 선택하여 도구 모음에서 앱을 실행합니다.](./media/csharp-console-calculator-button.png)

   콘솔 창이 열립니다.

1. 콘솔 창에서 앱을 확인한 다음, 프롬프트에 따라 **42** 및 **119** 숫자를 추가합니다.

   앱이 다음 스크린샷과 유사하게 표시될 것입니다.

    ![계산기 앱을 표시하고 수행할 작업에 대한 프롬프트가 포함된 콘솔 창](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>10진수 추가

계산기 앱은 현재 정수를 받고 반환합니다. 그러나 10진수를 허용하는 코드를 추가하면 더 정확해질 것입니다.

다음 스크린샷과 같이 앱을 실행하고 숫자 42를 119로 나누면 결과가 0(영)으로 정확하지 않습니다.

![결과로 10진수를 반환하지 않는 계산기 앱을 보여주는 콘솔 창](./media/csharp-console-calculator-nodecimal.png)

10진수를 처리하도록 코드를 수정해 보겠습니다.

1. `int` 변수의 각 인스턴스를 `float`로 변경합니다.

   (이 작업을 수행하는 데 도움이 되는 [찾기 및 바꾸기](../../ide/finding-and-replacing-text.md#find-and-replace-control) 컨트롤을 사용할 수 있습니다. 코드 편집기 내의 검색 컨트롤에 액세스하려면 **Crtl**+**F**를 누릅니다. 그런 다음, 검색 컨트롤에서 **다음 찾기** 단추 또는 **이전 찾기** 단추를 선택합니다. 바꾸기 옵션에 액세스하려면 **찾기** 텍스트 상자 옆의 단추를 선택합니다. 한 번에 하나를 바꾸려면 **바꾸기** 텍스트 상자 옆의 **다음 찾기** 단추를 선택합니다. 모든 일치 항목을 바꾸려면 **모두 바꾸기** 단추를 선택합니다.)

1. 계산기 앱을 다시 실행하고 숫자 **42**를 숫자 **119**로 나눕니다.

   이제 앱이 0 대신 10진수 숫자를 반환합니다.

    ![이제 결과로 10진수를 반환하는 계산기 앱을 보여주는 콘솔 창](./media/csharp-console-calculator-decimal.png)

그러나 앱은 10진수 결과만 생성합니다. 앱도 10진수를 계산할 수 있도록 코드를 몇 가지 수정해 보겠습니다.

1. `float` 변수의 각 인스턴스를 `double`로 변경합니다.

1. `Convert.ToInt32` 메서드의 각 인스턴스를 `Convert.ToDouble`로 변경합니다.

1. 계산기 앱을 실행하고 숫자 **42.5**를 숫자 **119.75**로 나눕니다.

   이제 앱이 10진수 값을 허용하고 해당 결과로 더 긴 10진수 숫자를 반환합니다.

    ![이제 10진수를 허용하고 그 결과로 더 긴 10진수 숫자를 반환하는 계산기 앱을 보여주는 콘솔 창](./media/csharp-console-calculator-usedecimals.png)

    ([코드 수정](#revise-the-code) 섹션에서 소수 자릿수를 수정합니다.)

## <a name="debug-the-app"></a>앱 디버그

기본 계산기 앱을 개선했지만 아직 사용자 입력 오류와 같은 예외를 처리할 수 있는 failsafes가 없습니다.

예를 들어 숫자를 0으로 나누거나 앱이 숫자 문자가 필요할 때 알파 문자를 입력하면(또는 그 반대로) 앱이 작동을 중지하고 오류를 반환합니다.

몇 가지 일반적인 사용자 입력 오류를 살펴보고 [디버거](../../debugger/debugger-feature-tour.md)에서 오류를 찾아 코드에서 수정하세요.

### <a name="fix-the-divide-by-zero-error"></a>"0으로 나누기" 오류 해결

숫자를 0으로 나누려고 하면 콘솔 앱이 중단됩니다. 그런 다음, Visual Studio는 코드 편집기에서 무엇이 잘못되었는지 보여줍니다.

   ![Visual Studio 코드 편집기에서 0으로 나누기 오류가 표시됩니다.](./media/csharp-console-calculator-dividebyzero-error.png)

이 오류를 처리하기 위해 코드를 변경해 보겠습니다.

1. `case "d":`와 `// Wait for the user to respond before closing`라는 주석 사이에 직접 표시되는 코드를 삭제합니다.

1. 다음 코드로 바꿉니다.

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

   코드를 추가한 후 `switch` 문이 있는 섹션은 다음 스크린샷과 비슷하게 표시되어야 합니다.

   ![Visual Studio 코드 편집기에서 수정된 "전환" 섹션](./media/csharp-console-calculator-switch-code.png)

이제 숫자를 0으로 나누면 앱은 다른 숫자를 요구할 것입니다. 더 나은 기능: 0이 아닌 숫자를 입력할 때까지 요청이 중지되지 않습니다.

   ![Visual Studio 코드 편집기에서 0으로 나누기 오류가 표시됩니다.](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>"format" 오류 해결

앱이 숫자 문자가 필요할 때 알파 문자를 입력하면(또는 그 반대로) 콘솔 앱이 중지됩니다. 그런 다음, Visual Studio는 코드 편집기에서 무엇이 잘못되었는지 보여줍니다.

   ![Visual Studio 코드 편집기에서 형식 오류가 표시됩니다.](./media/csharp-console-calculator-format-error.png)

이 오류를 해결하려면 이전에 입력한 코드를 리팩터링해야 합니다.

#### <a name="revise-the-code"></a>코드 수정

모든 코드를 처리하기 위해 `program` 클래스를 사용하는 대신 `calculator` 및 `program` 두 클래스로 앱을 나눕니다.  

`calculator` 클래스는 대량의 계산 작업을 처리하고 `program` 클래스는 사용자 인터페이스 및 오류 캡처 작업을 처리합니다.

이제 시작해 보겠습니다.

1. 다음 코드 블록 *후* 모두 삭제합니다.

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. 다음으로, 새 `calculator` 클래스를 다음과 같이 추가합니다.

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

1. 그런 다음, 새 `program` 클래스를 다음과 같이 추가합니다.

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
1. 프로그램을 실행할 **계산기**를 선택하거나 **F5** 키를 누릅니다.

1. 프롬프트에 따라 숫자 **42**를 숫자 **119**로 나눕니다. 앱은 다음과 비슷해야 합니다.

    ![잘못된 입력에 대해 수행할 작업과 오류 처리에 대한 프롬프트를 포함하는 리팩터링된 계산기 앱을 보여주는 콘솔 창](./media/csharp-console-calculator-refactored.png)

    콘솔 앱을 닫기 위해 선택할 때까지 더 많은 수식을 입력할 수 있는 옵션이 있습니다. 또한 결과의 소수 자릿수도 줄였습니다.

## <a name="close-the-app"></a>앱 닫기

1. 아직 수행하지 않았다면 계산기 앱을 닫습니다.

1. Visual Studio에서 **출력** 창을 닫습니다.

   ![Visual Studio에서 출력 창 닫기](./media/csharp-calculator-close-output-pane.png)

1. Visual Studio에서 **Ctrl**+**S**를 눌러 앱을 저장합니다.

1. Visual Studio를 닫습니다.

## <a name="code-complete"></a>코드 완료

이 tutortial 중 계산기 앱을 많이 변경했습니다. 이제 앱은 컴퓨팅 리소스를 보다 효율적으로 처리하고 대부분의 사용자 입력 오류를 처리합니다.

전체 코드는 다음과 같습니다.

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

## <a name="quick-answers-faq"></a>빠른 답변 FAQ

몇 가지 주요 개념을 강조 표시하는 빠른 FAQ는 다음과 같습니다. FAQ에는 자습서의 절차를 수행할 때 제기될 수 있는 질문에 대한 답변도 포함되어 있습니다.

### <a name="what-is-c"></a>C#이란?

C#은 .NET Framework 및 .NET Core에서 실행되는 형식이 안전한 프로그래밍 언어입니다. C#을 사용하여 Windows 애플리케이션, 클라이언트-서버 애플리케이션, 데이터베이스 애플리케이션, XML Web services, 분산 구성 요소 등을 만들 수 있습니다.

### <a name="what-is-visual-studio"></a>Visual Studio란?

Visual Studio는 개발자를 위한 통합 개발 생산성 도구입니다. 프로그램과 애플리케이션을 만드는 데 사용할 수 있는 프로그램으로 생각하면 됩니다.

### <a name="what-is-a-console-app"></a>콘솔 앱이란?

콘솔 앱은 입력을 받고 명령줄 창, 즉 콘솔에 출력을 표시합니다.

### <a name="what-is-net-core"></a>.NET Core란?

.NET Core는 .NET Framework의 다음 진화 단계입니다. NET Framework는 프로그래밍 언어 전체에서 코드를 공유할 수 있게 했고 .NET Core는 플랫폼 간에 코드를 공유하는 기능을 더합니다. 게다가 오픈 소스입니다.

.NET Framework 및 .NET Core 둘 다에 미리 빌드된 기능 라이브러리가 포함되어 있습니다. 사용자 코드를 실행할 가상 머신 역할을 하는 CLR(공용 언어 런타임)도 포함합니다.

### <a id="workload"></a>워크로드란 무엇이며 어떻게 추가하나요?

Visual Studio의 워크로드는 Visual Studio 설치를 사용자 지정하는 데 사용할 수 있는 프로그래밍 옵션 및 템플릿 집합을 나타냅니다. 워크로드는 선택한 프로그래밍 언어와 플랫폼에 필요한 도구만 설치합니다. 설치하는 방법은 다음과 같습니다.

#### <a name="option-1-use-the-new-project-dialog-box"></a>옵션 1: 새 프로젝트 대화 상자 사용

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 선택합니다.

   ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크 선택](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Visual Studio 설치 관리자가 시작됩니다. **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

   ![Visual Studio Installer에서 .NET Core 플랫폼 간 개발 워크로드](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>옵션 2: 도구 메뉴 모음 사용

1. **새 프로젝트** 대화 상자를 취소하고 나가 상단 메뉴 모음에서 **도구** > **도구 및 기능 가져오기**를 선택합니다.

1. Visual Studio 설치 관리자가 시작됩니다. **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

## <a name="next-steps"></a>다음 단계

축하합니다. 이 자습서를 마쳤습니다. 자세히 알아보려면 다음 자습서를 계속 진행하세요.

> [!div class="nextstepaction"]
> [C# 자습서](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>참고 항목

* [초보자를 위한 C# 기본 사항 비디오 과정](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)