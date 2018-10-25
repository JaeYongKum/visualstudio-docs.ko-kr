---
title: IDebugEnumField::GetValueFromStringCaseInsensitive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive
helpviewer_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive method
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 96e1e98a8d095a2fd7fc9c63b42267fc70cab065
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49933328"
---
# <a name="idebugenumfieldgetvaluefromstringcaseinsensitive"></a>IDebugEnumField::GetValueFromStringCaseInsensitive
이 메서드가 열거형 상수의 이름과 연관 된 값을 반환 하는 대/소문자 구분 검색을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetValueFromStringCaseInsensitive(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```csharp  
int GetValueFromStringCaseInsensitive(  
   string    pszValue,   
   out ulong pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszValue`  
 [in] 값을 검색할 원본에 대 한 이름을 지정 하는 문자열입니다. C + +에 대 한 사실은, 와이드 문자 문자열입니다.  
  
 `pValue`  
 [out] 연결된 된 숫자 값을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 에 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE`이면 이름, 열거형 또는 오류 코드의 일부가 아닙니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 대/소문자 구분 합니다. 대/소문자 구분 검색 (예를 들어, 등의 언어로 이름은 대/소문자 구분 하는 c + +) 필요한 경우 사용할 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)