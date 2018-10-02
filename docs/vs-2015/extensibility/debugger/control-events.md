---
title: 컨트롤 이벤트 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ac93da53f21b56df38a6ad597d7c4911075a670
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556675"
---
# <a name="control-events"></a>컨트롤 이벤트
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [컨트롤 이벤트](https://docs.microsoft.com/visualstudio/extensibility/debugger/control-events)합니다.  
  
프로그램의 제어 된 실행 하는 동안 이벤트를 보내야 합니다. 사용 하 여 전송 된 모든 이벤트를 [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) 인터페이스를 구현 해야 하는 특성이 합니다 [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) 메서드.  
  
## <a name="additional-methods"></a>추가 메서드  
 일부 이벤트는 다음과 같은 추가 메서드를 구현이 필요합니다.  
  
-   전송 합니다 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) 디버그 엔진 (DE) 초기화 될 때 인터페이스를 구현 해야 합니다 [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) 메서드.  
  
-   실행 제어와 같은 컨트롤 이벤트의 구현이 필요 합니다 [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) 하 고[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스입니다. **IDebugBreakEvent2** 비동기 중단에 대해서만 필요 합니다.  
  
-   구현 해야 함수를 한 단계씩 실행 합니다 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 인터페이스 및 해당 메서드.  
  
 중단점에서 파생 되는 이벤트 구현 해야 합니다 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)를 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), 및 [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) 인터페이스 뿐만 [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) 하 고 [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) 메서드.  
  
 비동기 식 평가 구현 해야 합니다 [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 인터페이스 및 해당 [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [및 GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) 메서드.  
  
 동기 이벤트 구현 해야 합니다 [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) 메서드.  
  
 스타일 문자열 출력을 작성 하 여 엔진에 대해 구현 해야 합니다 [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)

