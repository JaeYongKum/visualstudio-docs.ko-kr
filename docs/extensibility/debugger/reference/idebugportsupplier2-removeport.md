---
title: IDebugPortSupplier2::RemovePort | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::RemovePort
helpviewer_keywords:
- IDebugPortSupplier2::RemovePort
ms.assetid: f5c1fbf2-9084-46f2-a682-7db963928df2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6557d72561a15f8a330a0fc8eb9bc0b44a296f52
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49947838"
---
# <a name="idebugportsupplier2removeport"></a>IDebugPortSupplier2::RemovePort
포트를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RemovePort(   
   IDebugPort2* pPort  
);  
```  
  
```csharp  
int RemovePort(   
   IDebugPort2 pPort  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pPort`  
 [in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 제거할 포트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 활성 포트의 포트 공급자의 내부 목록에서 포트를 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)