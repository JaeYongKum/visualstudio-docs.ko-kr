---
title: IDebugDefaultPort2::QueryIsLocal | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a5becc75e76a0e219664ef07c148620fb2bc1e37
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900401"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
이 메서드는 로컬 컴퓨터에서이 포트 인지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 이 포트에는 로컬 (호출자와 같은 시스템) 인지 또는 `S_FALSE` 다른 컴퓨터에서 포트의 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)