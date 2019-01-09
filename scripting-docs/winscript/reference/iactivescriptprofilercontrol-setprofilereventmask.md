---
title: IActiveScriptProfilerControl::SetProfilerEventMask | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.SetProfilerEventMask
apilocation:
- scrobj.dll
ms.assetid: 207e192f-e12e-4fcb-b4d8-eaee50ecb86e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45ded6caec95f5421328be09e299af535765a9c2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086790"
---
# <a name="iactivescriptprofilercontrolsetprofilereventmask"></a>IActiveScriptProfilerControl::SetProfilerEventMask
스크립팅 엔진에서 발생 시킬 이벤트의 형식을 지정 하는 4 바이트 비트 마스크를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetProfilerEventMask(  
    [in] DWORD dwEventMask);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwEventMask`  
 [in] 이벤트의 형식을 지정 하는 4 바이트 비트 마스크입니다. 비트에 정의 된 [PROFILER_EVENT_MASK 열거형](../../winscript/reference/profiler-event-mask-enumeration.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환합니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링 사용 되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)