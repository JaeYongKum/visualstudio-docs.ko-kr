---
title: IDebugProgramHost2::GetHostMachineName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramHost2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramHost2::GetHostMachineName
ms.assetid: 4677ffe4-aa9b-4450-a63b-74cd3984d956
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db80058c70d84782c817a6f3a1679496d6019f77
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53848193"
---
# <a name="idebugprogramhost2gethostmachinename"></a>IDebugProgramHost2::GetHostMachineName
이 프로그램을 호스트 하는 프로세스에서 실행 되는 컴퓨터의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostMachineName(   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName(   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrHostMachineName`  
 [out] 컴퓨터의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)