---
title: JsInspectableToObject 함수 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc2c1cb12bf4b89d15e20a06c5366ac5fbc07faf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568643"
---
# <a name="jsinspectabletoobject-function"></a>JsInspectableToObject 함수
전달된 `IInspectable` 포인터의 프로젝션인 JavaScript 값을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `inspectable`  
 프로젝션해야 하는 `IInspectable`입니다.  
  
 `value`  
 `IInspectable`의 프로젝션인 JavaScript 값입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 프로젝션된 값은 스크립트에서 WinRT 개체를 호출하는 데 사용할 수 있습니다. 호스트가 COM 스레딩 규칙을 적용합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)