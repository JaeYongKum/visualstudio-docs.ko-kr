---
title: IDebugThread2::GetLogicalThread | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0034daecab2543d9a48a627a26a88ee84a872f73
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54945933"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
디버그 엔진에서이 메서드를 구현 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLogicalThread(   
   IDebugStackFrame2*     pStackFrame,  
   IDebugLogicalThread2** ppLogicalThread  
);  
```  
  
```csharp  
int GetLogicalThread(   
   IDebugStackFrame2        pStackFrame,  
   out IDebugLogicalThread2 ppLogicalThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 [in] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 스택 프레임을 나타내는 개체입니다.  
  
 `ppLogicalThread`  
 [out] 반환 된 `IDebugLogicalThread2` 관련된 논리 스레드를 나타내는 인터페이스입니다. 디버그 엔진 구현이 null 값으로 설정 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
 디버그 엔진 구현에서는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)