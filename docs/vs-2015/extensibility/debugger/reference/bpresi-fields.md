---
title: BPRESI_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 166ce76f427362601d4b0c4010d4814c3e165031
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51735782"
---
# <a name="bpresifields"></a>BPRESI_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

중단점을 해결 하는 방법에 대 한 검색할 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
typedef DWORD BPRESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
```  
  
## <a name="members"></a>멤버  
 BPRESI_BPRESLOCATION  
 초기화/사용 합니다 `bpResLocation` (중단점 해결 위치) 필드를 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조입니다.  
  
 BPRESI_PROGRAM  
 초기화/사용 된 `pProgram` 필드는 `BP_RESOLUTION_INFO` 구조입니다.  
  
 BPRESI_THREAD  
 초기화/사용 된 `pThread` 필드는 `BP_RESOLUTION_INFO` 구조입니다.  
  
 BPRESI_ALLFIELDS  
 모든 필드를 지정합니다.  
  
## <a name="remarks"></a>설명  
 에 전달 합니다 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) 의 필드를 표시 하는 방법을 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조는 초기화할 합니다.  
  
 이러한 플래그는의 필드를 나타내는 데도 `BP_RESOLUTION_INFO` 구조는 유효 하 고 사용 되는 해당 구조를 반환할 때.  
  
 이러한 값을 비트 결합할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)

