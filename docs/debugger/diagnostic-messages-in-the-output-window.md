---
title: 출력 창에 진단 메시지를 보낼 | Microsoft Docs
ms.custom: ''
ms.date: 04/25/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 27cec31b775ba5f8d201c81cbd65f5b161353986
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252299"
---
# <a name="send-diagnostic-messages-to-the-output-window"></a>출력 창에 진단 메시지를 보내기
런타임 메시지를 작성할 수 있습니다는 **출력** 사용 하 여 창을 합니다 <xref:System.Diagnostics.Debug> 클래스 또는 <xref:System.Diagnostics.Trace> 구성 요소인 클래스의는 <xref:System.Diagnostics> 클래스 라이브러리입니다. 사용 합니다 <xref:System.Diagnostics.Debug> 에 출력 하는 경우 클래스는 *디버그* 프로그램의 버전입니다. 사용 합니다 <xref:System.Diagnostics.Trace> 둘 다에서 출력 하려는 경우 클래스를 *디버그* 및 *릴리스* 버전입니다.  
  
## <a name="output-methods"></a>출력 메서드  
 <xref:System.Diagnostics.Trace> 클래스와 <xref:System.Diagnostics.Debug> 클래스에는 다음과 같은 출력 메서드가 있습니다.  
  
-   실행을 중단하지 않고 정보를 출력하는 여러 가지 `Write` 메서드. 이 메서드는 이전 Visual Basic 버전의 `Debug.Print` 메서드 대신 사용됩니다.  
  
-   지정된 조건이 실패할 경우 실행을 중단하고 정보를 출력하는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 메서드. 기본적으로 `Assert` 메서드는 해당 정보를 대화 상자에 표시합니다. 자세한 내용은 [관리 코드에 어설션](../debugger/assertions-in-managed-code.md)합니다.  
  
-   항상 실행을 중단하고 정보를 출력하는 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 메서드. 기본적으로 `Fail` 메서드는 정보를 대화 상자에 표시합니다.  
  
 응용 프로그램에서 프로그램 출력 이외에 **출력** 창에 대 한 정보를 표시할 수 있습니다.  
  
-   디버거에서 로드하거나 언로드한 모듈 정보  
  
-   throw된 예외 정보  
  
-   종료되는 프로세스 정보  
  
-   종료되는 스레드 정보  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [출력 창](../ide/reference/output-window.md)   
 [응용 프로그램 추적 및 조율](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [관리 코드 디버그](../debugger/debugging-managed-code.md)
