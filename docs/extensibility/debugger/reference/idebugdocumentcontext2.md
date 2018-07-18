---
title: IDebugDocumentContext2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2
helpviewer_keywords:
- IDebugDocumentContext2
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 06ff06086c0f293f70af7d9570cf72df4be85608
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107701"
---
# <a name="idebugdocumentcontext2"></a>IDebugDocumentContext2
이 인터페이스는 소스 파일 문서의 위치를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDocumentContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE) 소스 코드 수준 디버깅에 대 한 지원의 일부로이 인터페이스를 구현합니다. 소스 코드의 위치를 외에도이 인터페이스에서 컨텍스트를 비교 하 고 소스 코드 문서를 탐색 하기 위한 메서드를 제공 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 가장 일반적으로 몇 가지에 대 한 메서드 인터페이스는 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 및 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) 인터페이스의 경우이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugDocumentContext2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|이 문서 컨텍스트를 포함 하는 문서를 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|이 문서 컨텍스트를 포함 하는 문서의 표시 이름을 가져옵니다.|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|이 문서 컨텍스트와 연결 된 모든 코드 컨텍스트 목록을 검색 합니다.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|이 문서 컨텍스트와 연결 된 언어를 가져옵니다.|  
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|이 문서 컨텍스트의 파일 문의 범위를 가져옵니다.|  
|[GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|이 문서 컨텍스트의 파일 소스 범위를 가져옵니다.|  
|[Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|이 문서 컨텍스트 문서 컨텍스트를 지정 된 배열 비교합니다.|  
|[검색](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|지정된 된 수 있는 문이나 줄의 여 문서 컨텍스트를 이동합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)