---
title: IDebugMethodField::EnumArguments | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf62392118ed3ddfb2dfbfca06588f0935f3192d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719901"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
메서드를 호출 하는 데 필요한 각 인수의 형식에 대 한 열거자를 만듭니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumArguments( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumArguments(
   out IEnumDebugFields ppParams
);
```

#### <a name="parameters"></a>매개 변수
 `ppParams`

 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 인수 형식 목록을 나타내는 개체입니다. 인수가 없는 경우 null 값을 반환 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 S_OK를 반환 합니다. 또는 인수가 없으면 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="remarks"></a>설명
 각 요소는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 각 매개 변수의 형식을 나타내는 개체입니다. 호출 된 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) 각 매개 변수의 형식에 대 한 정보를 검색할 메서드입니다.

 매개 변수의 이름을 유형과 함께 필요한 경우 호출 된 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)