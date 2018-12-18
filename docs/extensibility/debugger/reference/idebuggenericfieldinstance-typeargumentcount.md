---
title: IDebugGenericFieldInstance::TypeArgumentCount | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TypeArgumentCount
- IDebugGenericFieldInstance::TypeArgumentCount
ms.assetid: e662c5ea-a5c1-478e-a268-5980dadffcd1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 066084853c63f7f824b27b365e9abf0f2d695970
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822243"
---
# <a name="idebuggenericfieldinstancetypeargumentcount"></a>IDebugGenericFieldInstance::TypeArgumentCount
이 인스턴스에 대 한 매개 변수 인수 형식의 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT TypeArgumentCount(  
   ULONG32* pcArgs  
);  
```  
  
```csharp  
int TypeArgumentCount(  
   ref uint pcArgs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcArgs`  
 [out에서] 이 인스턴스에 대 한 형식 매개 변수 인수의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 예를 들어 경우 목록\<int >,이 메서드는 1을 반환 경우 목록\<int, float2 >이 메서드는 2를 반환 합니다. 이 메서드는 형식 인수가 없는 경우 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)