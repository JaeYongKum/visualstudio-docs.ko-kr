---
title: IDebugEngine3::SetAllExceptions | Microsoft Docs
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
- IDebugEngine3::SetAllExceptions
helpviewer_keywords:
- IDebugEngine3::SetAllExceptions
ms.assetid: 8f03a6ac-a854-42f7-933c-a2df1b351975
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9da26eda5b369cfbaf5f405bf036a1ae6096cc85
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816842"
---
# <a name="idebugengine3setallexceptions"></a>IDebugEngine3::SetAllExceptions
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 모든 처리 중인 예외 상태를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAllExceptions(  
   EXCEPTION_STATE dwState  
);  
```  
  
```csharp  
int SetAllExceptions(  
   enum_EXCEPTION_STATE dwState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwState`  
 [in] 중 하나는 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)

