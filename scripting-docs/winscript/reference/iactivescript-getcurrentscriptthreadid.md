---
title: IActiveScript::GetCurrentScriptThreadID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetCurrentScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetCurrentScriptThreadID
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bac3b5755328e643c26c8f3746af6648d8ac06aa
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345801"
---
# <a name="iactivescriptgetcurrentscriptthreadid"></a>IActiveScript::GetCurrentScriptThreadID
현재 실행 중인 스레드에 대 한 스크립팅 엔진 정의 식별자를 검색합니다. 스크립트 스레드 실행 제어 메서드에 대 한 후속 호출에서 같은 식별자를 사용할 있습니다 합니다 [iactivescript:: Interruptscriptthread](../../winscript/reference/iactivescript-interruptscriptthread.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstidThread`  
 [out] 현재 스레드와 연결 된 스크립트 스레드 식별자를 받는 변수의 주소입니다. 이 식별자의 해석은 스크립팅 엔진에 그대로 있지만 Windows 스레드 식별자의 복사본 수 있습니다. Win32 스레드가 종료 되 면이 식별자가 할당 되지 않은 하 고 이후에 다른 스레드가에 할당할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_POINTER` 잘못 된 포인터를 지정 된 경우.  
  
## <a name="remarks"></a>설명  
 호스트 개체 또는 기본이 아닌 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)