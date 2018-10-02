---
title: '방법: 삽입된 한 코드 디버그 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.injected
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f283a8e526e343030636c62453e5eb03825a8f93
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553128"
---
# <a name="how-to-debug-injected-code"></a>방법: 삽입한 코드 디버깅
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 삽입 된 코드 디버그](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-injected-code)합니다.  
  
참고]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 특성을 사용하면 C++ 프로그래밍을 매우 단순화할 수 있습니다. 자세한 내용은 [개념](http://msdn.microsoft.com/library/563e7e7c-65e1-44f4-b0b2-da04a6c1bc9e)합니다. 일부 특성은 컴파일러가 직접 해석합니다. 프로그램 소스에 코드를 삽입하여 컴파일러가 컴파일할 수 있게 하는 특성도 있습니다. 이렇게 코드를 삽입하면 프로그래머가 써야 하는 코드의 양이 줄어들어 보다 쉽게 프로그래밍할 수 있습니다. 그러나 때때로 버그가 발생하여 삽입된 코드를 실행하는 동안 응용 프로그램에 문제가 생기기도 합니다. 이런 경우에는 삽입된 코드를 볼 수 있습니다. Visual Studio에서는 두 가지 방법으로 삽입된 코드를 볼 수 있습니다.  
  
-   삽입 된 코드에서 볼 수 있습니다 합니다 **디스어셈블리** 창입니다.  
  
-   사용 하 여 [/Fx](http://msdn.microsoft.com/library/14f0e301-3bab-45a3-bbdf-e7ce66f20560), 원본 및 삽입 된 코드가 포함 된 병합 된 소스 파일을 만들 수 있습니다.  
  
 합니다 **디스어셈블리** 창에는 소스 코드와 특성에 의해 삽입 된 코드에 해당 하는 어셈블리 언어 명령을 보여 줍니다. 또한 합니다 **디스어셈블리** 창에는 소스 코드 주석을 표시할 수 있습니다.  
  
### <a name="to-turn-on-source-annotation"></a>소스 주석을 설정하려면  
  
-   마우스 오른쪽 단추로 클릭 합니다 **디스어셈블리** 창에서 선택한 **소스 코드 표시** 바로 가기 메뉴에서.  
  
     소스 창에서 특성의 위치를 알고 있는 경우 사용할 수 바로 가기 메뉴에서 삽입된 된 코드를 찾으려고 합니다 **디스어셈블리** 창입니다.  
  
### <a name="to-view-injected-code"></a>삽입된 코드를 보려면  
  
1.  디버거는 중단 모드에 있어야 합니다.  
  
2.  소스 코드 창에서 보려는 삽입된 코드의 특성 앞에 커서를 놓습니다.  
  
3.  마우스 오른쪽 단추로 클릭 하 고 선택 **디스어셈블리로 이동** 바로 가기 메뉴에서.  
  
     특성의 위치를 현재 실행 위치 근처 인 경우 선택할 수 있습니다 합니다 **디스어셈블리** 창에서 합니다 **디버그** 메뉴.  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>현재 실행 위치에서 디스어셈블리 코드를 보려면  
  
1.  디버거는 중단 모드에 있어야 합니다.  
  
2.  **디버그** 메뉴에서 선택 **Windows**를 클릭 하 고 **디스어셈블리**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



