---
title: IDebugCodeContext2::GetDocumentContext | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCodeContext2::GetDocumentContext
helpviewer_keywords:
- IDebugCodeContext2::GetDocumentContext
ms.assetid: d552cc92-963f-43c1-949f-ae6b63a427b8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6f68bb0b855fa5e5fcc6cc2e81bd14c8f491abf6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543046"
---
# <a name="idebugcodecontext2getdocumentcontext"></a>IDebugCodeContext2::GetDocumentContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugCodeContext2::GetDocumentContext](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext)합니다.  
  
이 코드 컨텍스트에 해당 하는 문서 컨텍스트를 가져옵니다. 문서 컨텍스트를이 명령 생성 된 소스 코드에 해당 하는 소스 파일의 위치를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetDocumentContext(   
   IDebugDocumentContext2** ppSrcCxt  
);  
```  
  
```csharp  
int GetDocumentContext(   
   out IDebugDocumentContext2 ppSrcCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppSrcCxt`  
 [out] 반환 된 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 코드 컨텍스트에 해당 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 문서 컨텍스트를 생각할 수 있습니다 소스 파일의 위치와 코드 컨텍스트는 실행 스트림에 코드 명령의 위치입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)

