---
title: IActiveScriptAuthor::GetChars | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetChars
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetChars
ms.assetid: a73ba263-12f7-4d5f-b4c8-9ad7e2d5d3cb
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06e7a7cf276e589aaaa3c00ecab8cbf881942f82
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094330"
---
# <a name="iactivescriptauthorgetchars"></a>IActiveScriptAuthor::GetChars
요청된 완료 컨텍스트에 대 한 완료 문자 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetChars(  
   DWORD            fRequestedList,  
   BSTR             *pbstrChars  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fRequestedList`  
 [in] 요청된 완료 컨텍스트입니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|0x0001|왼쪽 열거형을 요청합니다.|  
|SCRIPT_CMPL_MEMBER_TRIGGER|0x0002|멤버 완료 컨텍스트를 요청합니다.|  
|SCRIPT_CMPL_PARAM_TRIGGER|0x0003|매개 변수 목록을 요청합니다.|  
|SCRIPT_CMPL_COMMIT|0x0004|매개 변수 목록의 요청 완료 합니다.|  
  
 `pbstrChars`  
 [out] 요청된 완료 컨텍스트에 해당 하는 문자입니다.  
  
|`fRequestedList` 매개 변수|반환 된 문자|  
|--------------------------------|-------------------------|  
|SCRIPT_CMPL_ENUM_TRIGGER|"."|  
|SCRIPT_CMPL_MEMBER_TRIGGER|"="|  
|SCRIPT_CMPL_PARAM_TRIGGER|"(,"|  
|SCRIPT_CMPL_COMMIT|"()"|  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)