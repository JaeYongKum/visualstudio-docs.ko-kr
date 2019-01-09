---
title: ISetNextStatement::CanSetNextStatement | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISetNextStatement.CanSetNextStatement
apilocation:
- scrobj.dll
ms.assetid: e2a54634-31ec-4d16-84e8-2b123845d876
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5288b0cffc3b8bfca0e995e67d4b3e4bf3a6b2e2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090131"
---
# <a name="isetnextstatementcansetnextstatement"></a>ISetNextStatement::CanSetNextStatement
이 메서드는 지정된 된 위치에 결정 실행할 코드의 다음 문을 실행 위치를 설정할 수 있는지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CanSetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 [in] 스택 프레임 개체에 대 한 포인터입니다.  
  
 `pCodeContext`  
 [in] 코드 컨텍스트 개체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|다음 문은 지정 된 코드 컨텍스트를 업데이트할 수 있습니다.|  
|`S_FALSE`|다음 문은 지정 된 코드 컨텍스트를 업데이트할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [ISetNextStatement 인터페이스](../../winscript/reference/isetnextstatement-interface.md)