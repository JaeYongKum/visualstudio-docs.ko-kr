---
title: IDebugEngine3::SetJustMyCodeState | Microsoft Docs
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
- IDebugEngine3::SetJustMyCodeState
helpviewer_keywords:
- IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fa066cddbf984fcdf2b636733948b3c6d71f044c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51753981"
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 JustMyCode 상태 정보에 대 한 디버그 엔진을 지시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fUpdate`  
 [in] 0이 아닌 값 (`TRUE`) 현재 정보를 업데이트 하려면 0 (`FALSE`)를 (이전에 설정한 모든 제외) 하는 모든 정보를 다시 설정 합니다.  
  
 `dwModules`  
 [in] 숫자의 정보 구조 `rgJMCSpec.`  
  
 `rgJMCSpec`  
 [in] 배열을 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) 구조를 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 JustMyCode는 사용자에 속하는 코드를 디버깅 하 고 시스템 코드와 같은 모든 중간 코드를 무시 하 여 개념이-소스 코드 시스템 코드에 사용할 수 있는 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)

