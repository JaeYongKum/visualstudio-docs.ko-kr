---
title: BP_LOCATION_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b4f483ca341055e7d041fe690dcdb4271138cf97
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922222"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
중단점 요청에 대 한 중단점 위치 유형을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```csharp  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## <a name="members"></a>멤버  
 BPLT_NONE  
 없는 중단점 위치를 지정합니다.  
  
 BPLT_FILE_LINE  
 파일 줄으로 중단점의 위치 유형을 지정합니다.  
  
 BPLT_FUNC_OFFSET  
 중단점 위치 형식 함수 오프셋으로 지정합니다.  
  
 BPLT_CONTEXT  
 중단점 위치 유형을 컨텍스트로 지정합니다.  
  
 BPLT_STRING  
 중단점 위치 형식의 문자열로 지정합니다.  
  
 BPLT_ADDRESS  
 주소로 중단점의 위치 유형을 지정합니다.  
  
 BPLT_RESOLUTION  
 중단점 위치 형식 해상도로 지정합니다.  
  
 BPLT_CODE_FILE_LINE  
 소스 코드의 줄으로 중단점의 위치 유형을 지정합니다.  
  
 BPLT_CODE_FUNC_OFFSET  
 코드 함수 오프셋으로 중단점의 위치 유형을 지정합니다.  
  
 BPLT_CODE_CONTEXT  
 코드 컨텍스트로 중단점의 위치 유형을 지정합니다.  
  
 BPLT_CODE_STRING  
 중단점 위치 형식 코드 문자열로 지정합니다.  
  
 BPLT_CODE_ADDRESS  
 중단점 위치 형식 코드 주소로 지정합니다.  
  
 BPLT_DATA_STRING  
 중단점 위치 형식 데이터 문자열로 지정합니다.  
  
 BPLT_TYPE_MASK  
 중단점 형식 값에서 추출할 수 있도록 하는 비트 마스크를 지정 합니다.  
  
 BPLT_LOCATION_TYPE_MASK  
 중단점 위치 유형 값에서 추출할 수 있도록 하는 비트 마스크를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 매개 변수로 전달 된 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md) 메서드.  
  
 중단점 위치 유형 및 위치 형식이 중단점 형식으로 구성 됩니다. 즉, 중단점 위치 형식 중단점 유형 뿐 되지 (예를 들어 `BPT_CODE`) 또는 위치 형식 (예를 들어 `BPLT_FILE_LINE`). 이 열거형에 포함 된 현재 지원 되는 모든 중단점 위치 형식에 대 한 미리 정의 된 상수 (`BPLT_CODE_FILE_LINE` 를 통해 `BPLT_DATA_STRING`).  
  
 `BPT_CODE` 및 `BPT_DATA` 의 멤버인 합니다 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) 열거형입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)