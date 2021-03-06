---
title: IDebugProcessEx2::Attach | Microsoft Docs
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
- IDebugProcessEx2::Attach
helpviewer_keywords:
- IDebugProcessEx2::Attach method
ms.assetid: f3334ed7-39bf-4d02-a338-36f567b9b287
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: daeef787ff380a17da2d5afa9c0f806f807b8598
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51745226"
---
# <a name="idebugprocessex2attach"></a>IDebugProcessEx2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 세션에서 프로세스를 디버깅 이제는 프로세스에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Attach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Attach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSession`  
 [in] 이 프로세스에 연결 세션을 고유 하 게 식별 하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 인터페이스에 전달 된 `pSession` 쿠키를 고유 하 게이 프로세스에 연결 하 여 세션 디버그 관리자를 식별 하는 값으로 서만 처리할지 제공 된 인터페이스의 메서드는 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)

