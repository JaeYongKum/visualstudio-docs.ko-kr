---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aade3935a49af176220e800647e6e821054bbb48
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56710359"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
이 필드에 연결 하는 모든 사용자 지정 특성에 대 한 열거자를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumCustomAttributes( 
   IEnumDebugCustomAttributes** ppEnum
);
```

```csharp
int EnumCustomAttributes(
   out IEnumDebugCustomAttributes ppEnum
);
```

#### <a name="parameters"></a>매개 변수
 `ppEnum`

 [out] 반환 합니다는 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) 사용자 지정 특성의 목록을 나타내는 개체, 그렇지 않으면 사용자 지정 특성이 없는 경우 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK 또는 반환 S_FALSE이이 필드에 사용자 지정 특성이 없는 경우. 그렇지 않으면 오류 코드 반환

## <a name="remarks"></a>설명
 필드에는 사용자 지정 특성이 여러 개 있을 수 있습니다.

## <a name="see-also"></a>참고 항목
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)
- [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)