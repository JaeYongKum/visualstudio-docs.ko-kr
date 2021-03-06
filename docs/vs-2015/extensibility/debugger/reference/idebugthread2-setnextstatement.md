---
title: IDebugThread2::SetNextStatement | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5956a57e9bd6db646091a5c0b7a0948d3cdac4bb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51776241"
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

지정 된 코드 컨텍스트에 현재 명령 포인터를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```csharp  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 사용 하도록 예약 됩니다. null 값으로 설정 합니다.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 실행 될 코드 위치를 설명 하는 개체 및 컨텍스트.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 다음 표에서 가능한 다른 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|다음 문이 프레임 스택에 심층적인 스택 프레임을 일 수 없습니다.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|다음 문을 스택의 모든 프레임을 사용 하 여 연결 되지 않습니다.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|일부 디버그 엔진에 예외가 발생 한 후 다음 문을 설정할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 명령 포인터는 다음 명령 또는 문 실행을 나타냅니다. 이 메서드는 소스 코드 줄을 다시 시도 하거나 다른 함수에 예를 들어 계속 실행 하도록 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)

