---
title: IDebugEngine3::LoadSymbols | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::LoadSymbols
helpviewer_keywords:
- IDebugEngine3::LoadSymbols
ms.assetid: c846a440-1d91-4d48-b8f1-82e902ae152b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fde88d8ecc31c9e1326b36da33c7fd96530ff86d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110769"
---
# <a name="idebugengine3loadsymbols"></a>IDebugEngine3::LoadSymbols
이 디버깅 엔진으로 디버깅 중인 모든 모듈에 대 한 기호 (필요)에 따라 로드 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadSymbols();  
```  
  
```csharp  
int LoadSymbols();  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 디버깅 엔진에서 참조 하는 모든 모듈에 대 한 디버깅 기호를 로드 합니다. 기호는 이미 않았습니다 로드 하는 경우에 로드 됩니다. 기호를 호출 하 여 설정 경로에서 검색 됩니다 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)