---
title: '디버깅 준비: 콘솔 프로젝트 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 516b2a6191cc76c3380875fda4679048e255f394
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49902082"
---
# <a name="debugging-preparation-console-projects"></a>디버깅 준비: 콘솔 프로젝트
콘솔 프로젝트 디버깅을 준비하는 과정은 Windows 프로젝트 디버깅을 준비하는 과정과 비슷하지만 몇 가지 사항을 추가로 고려해야 합니다. 자세한 내용은 [Windows Forms 응용 프로그램](../debugger/debugging-preparation-windows-forms-applications.md), 및 [디버깅 준비: Windows Forms 응용 프로그램 (.NET)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/sez9z95a(v=vs.100))합니다. 콘솔 응용 프로그램은 모두 비슷하므로 이 항목에서는 다음과 같은 프로젝트 형식을 다룹니다.  
  
- C# 콘솔 응용 프로그램  
  
- Visual Basic 콘솔 응용 프로그램  
  
- C++ 콘솔 응용 프로그램(.NET)  
  
- C++ 콘솔 응용 프로그램(Win32)  
  
  콘솔 응용 프로그램에 대한 명령줄 인수를 지정해야 할 수도 있습니다. 자세한 내용은 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md)를 [Visual Basic 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), 또는 [C# 디버그 구성에 대 한 프로젝트 설정 ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
  모든 프로젝트 속성과 마찬가지로 이러한 인수도 디버그 세션 사이와 Visual Studio 세션 사이에 지속적으로 적용됩니다. 따라서 이전에 디버깅 한 콘솔 응용 프로그램 이면 기억에 입력 된 이전 세션에서 인수가 있을 합니다  **\<프로젝트 > 속성 페이지** 대화 상자.  
  
  콘솔 응용 프로그램을 사용 하 여 **콘솔** 창 입력을 허용 하 고 출력 메시지를 표시 합니다. 쓸 합니다 **콘솔** 창에서 응용 프로그램 사용 해야 합니다는 **콘솔** Debug 개체 대신 개체입니다. 쓸 합니다 **Visual Studio 출력** 창 평소 처럼 Debug 개체를 사용 합니다. 사용자는 응용 프로그램에서 출력하는 위치를 정확하게 알아야 합니다. 정확한 위치를 모르면 잘못된 위치에서 메시지를 찾을 수 있습니다. 자세한 내용은 [Console 클래스](/dotnet/api/system.console)를 [Debug 클래스](/dotnet/api/system.diagnostics.debug), 및 [출력 창](../ide/reference/output-window.md)합니다.  
  
## <a name="starting-the-application"></a>응용 프로그램 시작  
 일부 콘솔 응용 프로그램은 시작되면 완료될 때까지 실행된 다음 종료됩니다. 이 동작은 실행을 중단하고 디버깅할 충분한 시간을 제공하지 않을 수 있습니다. 응용 프로그램을 디버깅할 수 있으려면 다음 절차 중 하나를 사용하여 응용 프로그램을 시작합니다.  
  
- 응용 프로그램 실행을 시작 하 고 중단점에 도달할 때까지 실행 됩니다.  
  
- 응용 프로그램이 시작되고 소스 코드의 첫째 줄에서 즉시 중단됩니다.  
  
- 소스 코드 창에서 줄을 마우스 오른쪽 단추로 클릭 하 고 선택 **커서까지 실행**합니다.  
  
   응용 프로그램이 시작되고 선택된 줄까지 실행되거나 해당 줄 전에 중단점이 적중되는 경우 중단점까지 실행됩니다.  
  
  콘솔 응용 프로그램을 디버깅할 때는 Visual Studio 대신 명령 프롬프트에서 응용 프로그램을 시작하는 경우가 있을 수 있습니다. 이 경우에는 명령 프롬프트에서 응용 프로그램을 시작하고 Visual Studio 디버거를 응용 프로그램에 연결할 수 있습니다. 자세한 내용은 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
  Visual Studio에서 콘솔 응용 프로그램을 시작 합니다 **콘솔** 창이 Visual Studio 창 뒤 나타나는 경우도 있습니다. Visual Studio에서 콘솔 응용 프로그램을 시작했는데 콘솔 창이 보이지 않으면 Visual Studio 창을 이동해 보십시오.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [Visual C++ 프로젝트 형식](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [디버거 보안](../debugger/debugger-security.md)