---
title: '방법: 프로그램에서 충돌이 발생 하는 DLL 찾기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40f27e0bec20e1dd037beaa5f60ea648c0ccb171
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257099"
---
# <a name="how-to-find-which-dll-your-program-crashed-in-c-c-visual-basic-f"></a>방법: 프로그램에서 충돌이 발생 하는 DLL 찾기 (C#, c + +, Visual Basic의 경우 F#)
  
 시스템 DLL 또는 다른 사람의 코드를 호출하는 동안 응용 프로그램에 충돌이 발생하면 충돌 발생 시 활성 상태였던 DLL을 찾아야 합니다. 사용자 프로그램 외부 DLL 충돌을 발생 하는 경우 사용 하 여 위치를 식별할 수 있습니다 합니다 **모듈** 창입니다.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>모듈 창을 사용하여 충돌이 발생한 위치를 찾으려면  
  
1.  충돌이 발생한 주소를 기록합니다.

    주소 오류 메시지에 표시 되지 않는 경우 대체 방법을 사용 하 여 DLL을 식별 해야 합니다. 시스템 DLL을 생각 하면 [기호를 로드](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) 디버깅 하는 경우 Microsoft 기호 서버에서. 그렇지 않은 경우 해야 할 수 있습니다 [덤프 파일을 만들도록](../debugger/using-dump-files.md) 사용 하 여 정보를 대신 힙. 다양 한 [도구](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/) 덤프 파일을 만드는 데 사용할 수 있습니다.
  
2.  에 **디버그** 메뉴 선택 **Windows**를 클릭 하 고 **모듈**합니다.  
  
3.  에 **모듈** 창 찾기 합니다 **주소** 열입니다. 이 열을 표시하려면 스크롤 막대를 사용해야 할 수도 있습니다.  
  
4.  클릭 합니다 **주소** 주소별로 Dll을 정렬 하려면 열 맨 위에 있는 단추입니다.  
  
5.  정렬된 목록을 조사하여 충돌 위치가 속하는 주소 범위를 가진 DLL을 찾습니다.  
  
6.  확인 합니다 **이름** 및 **경로** DLL 이름 및 경로 참조 하는 열.  
  
## <a name="see-also"></a>참고 항목  
 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md)   
 [방법: 모듈 창 사용](../debugger/how-to-use-the-modules-window.md)