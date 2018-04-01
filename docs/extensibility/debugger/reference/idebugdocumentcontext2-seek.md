---
title: IDebugDocumentContext2::Seek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ec88bb39a8319fba752b52023fdc4fb0b5a6c22a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
지정된 된 수 있는 문이나 줄의 여 문서 컨텍스트를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Seek(   
   int                      nCount,  
   IDebugDocumentContext2** ppDocContext  
);  
```  
  
```cpp  
int Seek(   
   int                        nCount,  
   out IDebugDocumentContext2 ppDocContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nCount`  
 [in] 문 또는 문서 컨텍스트에 따라 든, 이동 하려면 줄의 수입니다.  
  
 `ppDocContext`  
 [out] 새 반환 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 개체의 새 위치로 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)