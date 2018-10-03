---
title: BP_COND_STYLE | Microsoft Docs
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
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea5e0df33ef462d6b1b8bbe013f30baab894ea82
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543368"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [BP_COND_STYLE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-cond-style)합니다.  
  
보류 중인 중단점 조건 스타일을 지정 하 고 바인딩된 중단점.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```csharp  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## <a name="members"></a>멤버  
 BP_COND_NONE  
 중단점의 위치에 도달 하면 중단점을 발생 시킵니다. 중단점 조건 지정 없습니다.  
  
 BP_COND_WHEN_TRUE  
 중단점이 설정 된 조건식을 연결 하는 경우로 중단점이 발생 `true`합니다.  
  
 BP_COND_WHEN_CHANGED  
 발생 조건 식의 값 중단점과 연결 된 경우에 중단점 이전 해당 평가에서 변경 되었습니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 합니다 `styleCondition` 의 멤버는 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
