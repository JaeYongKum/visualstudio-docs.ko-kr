---
title: IDebugObject::IsNullReference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 25de5fdde9e0d834b98f09d2f5c9e2444f8a9d0e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706901"
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
이 개체는 null 참조 인지 테스트 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsNullReference( 
   BOOL* pfIsNull
);
```

```csharp
int IsNullReference(
   out int pfIsNull
);
```

#### <a name="parameters"></a>매개 변수
 `pfIsNull`

 [out] 0이 아닌 값을 반환 합니다 (`TRUE`)이이 개체는 null 참조 이면 그렇지 않으면 0을 반환 합니다 (`FALSE`).

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.

## <a name="remarks"></a>설명
 Null 참조에 할당 되지 않았습니다 하는 개체 또는 빈 개체를 의미 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)