---
title: IDebugProcessEx2::AddImplicitProgramNodes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 22f6cadaa88d6cc87ec70451d9da850cd49b7753
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31117022"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
이 메서드는 지정 된 각 디버그 엔진 (DE)에 대 한 프로그램 노드를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```csharp  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidLaunchingEngine`  
 [in] `GUID` 프로그램을 시작 하는 사용 하는 것 (및 자체 프로그램 노드를 추가 하려면 가정)는 DE의 합니다.  
  
 `rgguidSpecificEngines`  
 [in] 배열 `GUID`DEs 노드를 추가할 응용 프로그램의 s입니다.  
  
 `celtSpecificEngines`  
 [in] 수가 `GUID`에 s는 `rgguidSpecificEngines` 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [노드 프로그램](../../../extensibility/debugger/program-nodes.md) 에 나열 된 각 DE에 추가할 수 `rgguidSpecificEngines`-시작 엔진은 제외 하 고 (에 지정 된 `guidLaunchingEngine`), 프로그램을 시작할 때 자체 프로그램 노드를 추가 가정 된 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [프로그램 노드](../../../extensibility/debugger/program-nodes.md)