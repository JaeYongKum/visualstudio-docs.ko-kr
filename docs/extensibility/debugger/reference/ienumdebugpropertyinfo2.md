---
title: IEnumDebugPropertyInfo2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugPropertyInfo2
helpviewer_keywords:
- IEnumDebugPropertyInfo2
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2cd2e15aa02004f6fe22f08894a7f3eec4c1ea22
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31124758"
---
# <a name="ienumdebugpropertyinfo2"></a>IEnumDebugPropertyInfo2
이 인터페이스를 열거 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugPropertyInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)는 특정 속성에 대 한 정보를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 는 특정 속성의 자식을 나타내는이 인터페이스를 가져올 수 있습니다. 호출 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 특정 스택 프레임의 속성을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugPropertyInfo2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|지정된 된 수의 검색 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 열거형 시퀀스에는 구조입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|지정 된 개수의 건너뜁니다 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 열거형 시퀀스에는 구조입니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|개수를 가져옵니다 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조에는 열거자입니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 속성은 계층 이름, 값, 주소 및 형식을 포함할 수 있는 정보 뿐만 아니라 연결된 속성 개체 또는 스택 프레임에 적합 한 기타 정보입니다. 참조 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 내용을 확인 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)