---
title: IDebugApplication::StepOutComplete | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StepOutComplete
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StepOutComplete
ms.assetid: 9675b214-7be5-4cf7-a63f-7865f3c54371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1798d347fff11a49b945519fd20c370eca75d590
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089923"
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
단일 단계 모드에서 언어 엔진을 호출자에 게 반환를 프로세스 디버그 관리자에 게 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수 없이 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 언어 엔진 해당 호출자에 게 반환 하기 바로 전에 단일 단계 모드에서이 메서드를 호출 합니다. 프로세스 디버그 관리자는 첫 번째 기회에 줄 바꿈되는 다른 모든 스크립트 엔진에 알리기 위해이 기회를 사용 합니다. 이 방법은 모드의 구현 방법을 언어 간 단계에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)