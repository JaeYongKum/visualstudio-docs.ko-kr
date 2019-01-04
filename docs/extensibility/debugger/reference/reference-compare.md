---
title: REFERENCE_COMPARE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- REFERENCE_COMPARE
helpviewer_keywords:
- REFERENCE_COMPARE enumeration
ms.assetid: e31cdc78-f621-498b-9ca4-aefa790b9f6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e8bec2d34abd463ef196b957c1d19f38954bd998
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53944975"
---
# <a name="referencecompare"></a>REFERENCE_COMPARE
참조에 대 한 비교의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_REFERENCE_COMPARE {   
   REF_COMPARE_EQUAL        = 0x0001,  
   REF_COMPARE_LESS_THAN    = 0x0002,  
   REF_COMPARE_GREATER_THAN = 0x0003  
};  
typedef DWORD REFERENCE_COMPARE;  
```  
  
```csharp  
public enum enum_REFERENCE_COMPARE {   
   REF_COMPARE_EQUAL        = 0x0001,  
   REF_COMPARE_LESS_THAN    = 0x0002,  
   REF_COMPARE_GREATER_THAN = 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 REF_COMPARE_EQUAL  
 같음 비교를 지정합니다.  
  
 REF_COMPARE_LESS_THAN  
 작음 지정-보다 비교 합니다.  
  
 REF_COMPARE_GREATER_THAN  
 큼 지정-보다 비교 합니다.  
  
## <a name="remarks"></a>설명  
 인수로 전달 된 [비교](../../../extensibility/debugger/reference/idebugreference2-compare.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugreference2-compare.md)