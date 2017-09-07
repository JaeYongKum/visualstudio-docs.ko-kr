---
title: IDebugCoreServer3::GetConnectionProtocol | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer3::GetConnectionProtocol
helpviewer_keywords:
- IDebugCoreServer3::GetConnectionProtocol
ms.assetid: 368ced5b-c5d9-4090-a5b4-26ff400d1a55
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 8901f9fff01ecdfe21e3731df8b2d155fe250ac2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# IDebugCoreServer3::GetConnectionProtocol
디버그 패키지가 서버 간의 통신에 사용 되는 프로토콜을 나타내는 값을 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetConnectionProtocol(  
   CONNECTION_PROTOCOL* pProtocol  
);  
```  
  
```csharp  
int GetConnectionProtocol(  
   CONNECTION_PROTOCOL[] pProtocol  
);  
```  
  
#### 매개 변수  
 `pProtocol`  
 [out] 값 중 하나를 반환 된 [CONNECTION_PROTOCOL](../../../extensibility/debugger/reference/connection-protocol.md) 열거 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [CONNECTION_PROTOCOL](../../../extensibility/debugger/reference/connection-protocol.md)
