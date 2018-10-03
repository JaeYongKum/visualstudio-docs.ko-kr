---
title: IDebugQueryEngine2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugQueryEngine2
helpviewer_keywords:
- IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f80e8b44326cb082c8f6428365bad2575c317da6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549483"
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugQueryEngine2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugqueryengine2)합니다.  
  
이 인터페이스는 세션을 디버그 관리자 (SDM) 디버그 엔진 (DE)를 나타내는 인터페이스를 검색할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugQueryEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 가장 일반적인 DE 인터페이스를 구현 하는 개체에서이 인터페이스를 구현 하는 DE (같은 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)를 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), 및 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md))에서 에 대 한 액세스를 허용 하려면 합니다 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 자체는 DE의 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 호출 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 일반적인 DE 인터페이스이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugQueryEngine2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|사용자 지정 디버그 엔진 (DE) 인터페이스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 일반적으로 구현 하는 개체에서 구현 된 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 함수를 단계별로 실행 하면 인과 관계 순서, 즉 디버거는 함수에서 단계별로 실행 하는 경우를 지원 하기 위해 인터페이스는 다음 함수 실행 되지 않을 수 있습니다 이전 함수 스택에 있지만 다른 스레드의 함수 모두. "인과 관계"의 정의 참조 하세요. 합니다 [Visual Studio 디버거 용어집](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
