---
title: BP_LOCATION_DATA_STRING | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae83bf4d0f8ba6435a962f5c1477e460d69ae27f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100600"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
사용자는 통합된 개발 환경 (IDE)에서 입력할 수 있는 문자열을 기반으로 하는 데이터 중단점을 설정 하기 위한 사용.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## <a name="members"></a>멤버  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 중단점이 발생 하는 스레드를 나타내는 개체입니다.  
  
 `bstrContext`  
 코드 내에서 중단점 호출 스택에 보듯이 메서드 또는 함수 이름, 일반적으로의 컨텍스트.  
  
 `bstrDataExpr`  
 데이터 문자열 중단점을 설정 하는 사용자가 입력 합니다.  
  
 `dwNumElements`  
 중단점이 발생 하는 데이터 문자열에 있는 요소의 수입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는의 구성원은 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체의 일부로 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)