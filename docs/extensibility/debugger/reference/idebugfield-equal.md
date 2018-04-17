---
title: IDebugField::Equal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b2d195c28123cc786c9a5a97add98b7f67d499b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
이 메서드는이 필드는 지정 된 필드의 일치 여부를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```csharp  
int Equal(  
   IDebugField pField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pField`  
 [in] 이 이와 비교할 필드입니다.  
  
## <a name="return-value"></a>반환 값  
 필드 같으면 반환 `S_OK`합니다. 다른 필드의 경우 반환 `S_FALSE.` 그렇지 않은 경우 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)