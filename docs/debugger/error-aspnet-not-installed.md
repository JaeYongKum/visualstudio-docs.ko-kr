---
title: '오류: ASP.NET이 설치 되어 있지 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 41ec708b25bc74eb1f566981ee4bbcdc23827087
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "53902112"
---
# <a name="error-aspnet-not-installed"></a>오류: ASP.NET이 설치되어 있지 않음
이 오류는 디버깅하려는 컴퓨터에 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 제대로 설치되어 있지 않을 때 발생합니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 설치되지 않았거나 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]을 먼저 설치하고 나중에 IIS를 설치했을 수 있습니다.  
  
### <a name="to-reinstall-aspnet"></a>ASP.NET을 다시 설치하려면  
  
1. 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
   ```cmd
   \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
   ```  
  
    여기서 *버전* v1.0.370) 컴퓨터에 설치 된.NET Framework의 버전 번호를 나타냅니다. 프레임 워크 버전을 확인 하 여 확인할 수 있습니다는 `\WINDOWS\Microsoft.NET\Framework` 디렉터리입니다.  
  
   > [!NOTE]
   >  Windows Server 2003에서는 제어판의 **프로그램 추가 또는 제어**를 사용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]을 설치할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 애플리케이션 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
