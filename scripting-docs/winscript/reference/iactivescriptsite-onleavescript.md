---
title: IActiveScriptSite::OnLeaveScript | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnLeaveScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnLeaveScript
ms.assetid: 79af0e22-fbe3-4fae-8a5f-7af8b857678d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da39058a8f069c4799835108372d11849d86444e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160747"
---
# <a name="iactivescriptsiteonleavescript"></a>IActiveScriptSite::OnLeaveScript
스크립트 코드를 실행 스크립팅 엔진에 반환 되는 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OnLeaveScript(void);  
```  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `S_OK`가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 스크립팅 엔진을 입력 하는 호출 응용 프로그램에 제어를 반환 하기 전에이 메서드를 호출 해야 합니다. 예를 들어 경우 스크립트는 개체를 호출 하는 스크립팅 엔진에서 처리 하는 이벤트를 발생 시킵니다, 스크립팅 엔진 호출 해야 합니다 [IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md) 이벤트를 실행 하기 전에 메서드 호출해야합니다`IActiveScriptSite::OnLeaveScript`이벤트를 발생 시킨 개체를 반환 하기 전에 이벤트를 실행 한 후입니다. 이 메서드를 호출을 중첩할 수 있습니다. 호출할 때마다 `IActiveScriptSite::OnEnterScript` 이 메서드를 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)