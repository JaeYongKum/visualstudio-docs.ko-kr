---
title: IActiveScriptProfilerCallback::OnFunctionExit | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionExit
apilocation:
- scrobj.dll
ms.assetid: a5d21715-2b0b-423e-8644-f04a9e7cde3d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb3f71e9a8a383e2362bacb17698f4eec58f464e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092208"
---
# <a name="iactivescriptprofilercallbackonfunctionexit"></a>IActiveScriptProfilerCallback::OnFunctionExit
개체는 호출 하는 함수를 실행 하는 완성 된 스크립팅 엔진 아님을 문서 개체 모델 (DOM)에 대 한 호출 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OnFunctionExit(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptId`  
 [in] 함수가 포함 된 스크립트의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `functionId`  
 [in] 함수의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 호출 DOM 호출용 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md) 대신 `IActiveScriptProfilerCallback::OnFunctionExit`합니다. Dom의 고유한 메서드 및 속성 수가 많기 때문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)   
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)