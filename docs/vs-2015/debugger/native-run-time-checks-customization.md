---
title: 네이티브 런타임 검사 사용자 지정 | Microsoft Docs
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
- vs.debug.crt
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- runtime_checks pragma
- debugger, native run-time checks
- /RTC compiler option [C++], native run-time checks
- customizing CRT error checking
- native run-time checks, customizing
ms.assetid: 76a365fe-6439-49db-8603-34058b78e5a8
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65aaef84c96605eb0ac5a4836c637c2990a15477
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556956"
---
# <a name="native-run-time-checks-customization"></a>네이티브 런타임 검사 사용자 지정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [네이티브 런타임 검사 사용자 지정](https://docs.microsoft.com/visualstudio/debugger/native-run-time-checks-customization)합니다.  
  
로 컴파일할 때 **/RTC** (런타임 검사) 사용 하 여 또는 `runtime_checks` pragma를 C 런타임 라이브러리 네이티브 런타임 검사를 제공 합니다. 다음과 같은 경우에는 CRT 런타임 검사를 사용자 지정할 수도 있습니다.  
  
-   런타임 검사 메시지를 파일 또는 기본 위치 이외의 대상으로 라우팅하는 경우  
  
-   타사 디버거에서 런타임 검사 메시지의 출력 대상을 지정하는 경우  
  
-   C 런타임 라이브러리의 릴리스 버전으로 컴파일한 프로그램의 런타임 검사 메시지를 보고하는 경우. 라이브러리의 릴리스 버전은 `_CrtDbgReportW`를 사용하여 런타임 오류를 보고하지 않습니다. 대신 표시 됩니다는 **Assert** 각 런타임 오류에 대 한 대화 상자.  
  
 런타임 오류 검사를 사용자 지정하는 방법은 다음과 같습니다.  
  
-   런타임 오류 보고 함수를 작성합니다. 자세한 내용은 [방법: 런타임 오류 보고 함수 작성](../debugger/how-to-write-a-run-time-error-reporting-function.md)합니다.  
  
-   오류 메시지 대상을 사용자 지정합니다.  
  
-   런타임 검사 오류에 대한 정보를 쿼리합니다.  
  
## <a name="customize-the-error-message-destination"></a>오류 메시지 대상 사용자 지정  
 `_CrtDbgReportW`를 사용하여 오류를 보고하는 경우 `_CrtSetReportMode`를 사용하여 오류 메시지의 대상을 지정할 수 있습니다.  
  
 사용자 지정 보고 함수를 사용하는 경우 `_RTC_SetErrorType`을 사용하여 오류를 보고 형식에 연결합니다.  
  
## <a name="query-for-information-about-run-time-checks"></a>런타임 검사에 대한 정보 쿼리  
 `_RTC_NumErrors`는 런타임 오류 검사에서 발견된 오류 형식의 수를 반환합니다. 각 오류에 대한 간단한 설명을 보려면 0에서 `_RTC_NumErrors` 반환 값까지 반복하면서 반복 값을 각 루프의 `_RTC_GetErrDesc`로 전달합니다. 자세한 내용은 [_RTC_NumErrors](http://msdn.microsoft.com/library/7e82adae-38e2-4f8b-bc0b-37bda8109fd1) 하 고 [_RTC_GetErrDesc](http://msdn.microsoft.com/library/7994ec2b-5488-4fd4-806d-a166c9a9f927)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 네이티브 런타임 검사 사용](../debugger/how-to-use-native-run-time-checks.md)   
 [runtime_checks](http://msdn.microsoft.com/library/ae50b43f-f88d-47ad-a2db-3389e9e7df5b)   
 [_CrtDbgReport, _CrtDbgReportW](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc)




