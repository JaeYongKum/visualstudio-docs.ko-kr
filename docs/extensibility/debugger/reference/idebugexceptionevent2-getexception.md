---
title: IDebugExceptionEvent2::GetException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExceptionEvent2::GetException
helpviewer_keywords:
- IDebugExceptionEvent2::GetException
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fc844885a7efa1784b985eb3901de80a47c5efe4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116453"
---
# <a name="idebugexceptionevent2getexception"></a>IDebugExceptionEvent2::GetException
이 이벤트를 발생 시킨 예외에 대 한 자세한 설명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetException(   
   EXCEPTION_INFO* pExceptionInfo  
);  
```  
  
```csharp  
int GetException(   
   EXCEPTION_INFO[] pExceptionInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pExceptionInfo`  
 [out에서] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 는 예외에 대 한 설명을 포함 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [C + + 전용] 호출자가 해제의 모든 문자열에 대 한는 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 해제 뿐만 아니라 구조체는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 구조에는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)