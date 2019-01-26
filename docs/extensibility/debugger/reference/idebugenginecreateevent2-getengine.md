---
title: IDebugEngineCreateEvent2::GetEngine | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineCreateEvent2::GetEngine
helpviewer_keywords:
- IDebugEngineCreateEvent2::GetEngine
ms.assetid: 187d24ed-9f9a-4418-a0ef-b8a19f54652c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e970689248dd6de163c68e8c3854f55bc428eef4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54974830"
---
# <a name="idebugenginecreateevent2getengine"></a>IDebugEngineCreateEvent2::GetEngine
새로 만든된 디버그 엔진 (DE)를 나타내는 개체를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEngine(   
   IDebugEngine2** pEngine  
);  
```  
  
```csharp  
int GetEngine(   
   out IDebugEngine2 pEngine  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pEngine`  
 [out] 반환 된 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 새로 만든된 DE를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)