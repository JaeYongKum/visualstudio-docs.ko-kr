---
title: IActiveScriptSiteDebug32::GetApplication | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 533d770d-06a4-4693-873e-255c9c6f0df0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: c71e33445db7745f71e374c586d079a9665776b2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087906"
---
# <a name="iactivescriptsitedebug32getapplication"></a>IActiveScriptSiteDebug32::GetApplication
이 스크립트 사이트와 연결 된 디버그 응용 프로그램 개체를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppda`  
 [out] 스크립트 사이트에 연결 된 디버그 응용 프로그램 개체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|호스트 직접 디버깅이 지원 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 `GetApplication` 메서드는 각 스크립트 속해 있는 응용 프로그램 개체를 정의 하는 스마트 호스트에 대 한 방법을 제공 합니다. 스크립트 엔진을 포함 하는 응용 프로그램을 가져오고 편의 위해이 메서드를 호출 하려고 시도해 야 `IProcessDebugManager::GetDefaultApplication` 실패 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteDebug32 인터페이스](../../winscript/reference/iactivescriptsitedebug32-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)