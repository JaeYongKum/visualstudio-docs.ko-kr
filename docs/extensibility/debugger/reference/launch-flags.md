---
title: LAUNCH_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- LAUNCH_FLAGS
helpviewer_keywords:
- LAUNCH_FLAGS enumeration
ms.assetid: f51aab02-d257-4302-bb79-b7d8ba9ac4e5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f151391de60bea7164f61edfe608c425534c9b44
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934324"
---
# <a name="launchflags"></a>LAUNCH_FLAGS
디버그 시작 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_LAUNCH_FLAGS {   
   LAUNCH_DEBUG      = 0x0000,  
   LAUNCH_NODEBUG    = 0x0001,  
   LAUNCH_ENABLE_ENC = 0x0002,  
   LAUNCH_MERGE_ENV  = 0x0004  
};  
typedef DWORD LAUNCH_FLAGS;  
```  
  
```csharp  
public enum enum_LAUNCH_FLAGS {   
   LAUNCH_DEBUG      = 0x0000,  
   LAUNCH_NODEBUG    = 0x0001,  
   LAUNCH_ENABLE_ENC = 0x0002,  
   LAUNCH_MERGE_ENV  = 0x0004  
};  
```  
  
## <a name="members"></a>멤버  
 LAUNCH_DEBUG  
 디버깅에 대 한 프로세스를 시작 합니다.  
  
 LAUNCH_NODEBUG  
 디버그 하지 않고 프로세스를 시작 합니다.  
  
 LAUNCH_ENABLE_ENC  
 사용 되지 않으며, 사용 하지 마십시오.  
  
 LAUNCH_MERGE_ENV  
 프로세스를 시작 하 고 시작 하는 호스트를 사용 하 여 환경을 병합 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값을 인수로 전달 되는 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 메서드.  
  
 이러한 플래그는 비트과 결합 될 수 `OR`입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)