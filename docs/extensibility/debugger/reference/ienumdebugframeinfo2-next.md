---
title: IEnumDebugFrameInfo2::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugFrameInfo2::Next
helpviewer_keywords:
- IEnumDebugFrameInfo2::Next
ms.assetid: 64a64eeb-5dea-4119-8a22-03771015d1e5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0956c8deee664e457e6f509683cf8d42e1659ce6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916954"
---
# <a name="ienumdebugframeinfo2next"></a>IEnumDebugFrameInfo2::Next
열거형에서 다음 요소 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
   ULONG       celt,  
   FRAMEINFO** rgelt,  
   ULONG*      pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint        celt,  
   FRAMEINFO[] rgelt,  
   ref uint    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 요소의 수입니다. 또한 최대 크기를 지정 된 `rgelt` 배열입니다.  
  
 `rgelt`  
 [out에서] 배열을 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 채울 요소입니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수를 반환 합니다. `rgelt`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 요소의 요청 된 수보다 적은; 반환 될 수 있으면이 고, 그렇지 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)