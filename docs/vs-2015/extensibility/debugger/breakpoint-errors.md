---
title: 중단점 오류 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7614a82e4c25c2896fa98ba9685de0a6a5920fbc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51770809"
---
# <a name="breakpoint-errors"></a>중단점 오류
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음 코드에 중단점을 바인딩하려는 경우 프로세스를 설명 하지만 실패 합니다.  
  
## <a name="troubleshooting-a-breakpoint-error"></a>중단점 오류 문제 해결  
  
1.  디버그 엔진 (DE) 보냅니다는 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) 세션 디버그 관리자 (SDM).  
  
2.  SDM 호출 [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 * * `ppErrorBP`) 오류 중단점을 가져오려고 합니다.  
  
3.  SDM 호출 [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) 오류 중단점이 발생 한 보류 중인 중단점을 가져오려고 합니다.  
  
4.  SDM 호출 [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) 오류 중단점을 바인딩하지 못했습니다. 이유는 이유를 가져오려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)

