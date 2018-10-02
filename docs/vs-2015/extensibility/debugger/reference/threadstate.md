---
title: THREADSTATE | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5b62e8770449fc71a47d325d933b54b2090f59e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553191"
---
# <a name="threadstate"></a>THREADSTATE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [THREADSTATE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/threadstate)합니다.  
  
스레드의 상태를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```csharp  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## <a name="members"></a>멤버  
 THREADSTATE_RUNNING  
 스레드가 실행 중임을 나타냅니다.  
  
 THREADSTATE_STOPPED  
 스레드가 중단점으로 인해 중지 되었음을 나타냅니다.  
  
 THREADSTATE_FRESH  
 스레드를 만든 했지만 코드가 아직 실행 되지 않음을 나타냅니다.  
  
 THREADSTATE_DEAD  
 스레드 소멸 임을 나타냅니다.  
  
 THREADSTATE_FROZEN  
 스레드를 고정 나타냅니다 (없습니다 실행을 수행할 수 있습니다.).  
  
## <a name="remarks"></a>설명  
 에 사용 되는 합니다 `dwThreadState` 필드를 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)
