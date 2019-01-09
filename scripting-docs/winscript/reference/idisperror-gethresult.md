---
title: IDispError::GetHresult | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetHresult
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetHresult
ms.assetid: a14d566e-473f-497b-a2f9-85331433e6c9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08020ea38c687cb0f69b1108935fd79802cc3120
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086283"
---
# <a name="idisperrorgethresult"></a>IDispError::GetHresult
오류 코드를 검색 합니다 `IDispError` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetHresult(  
   HRESULT*  phr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phr`  
 [out] 오류 코드를 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 오류 코드를 검색 하는이 메서드는 `IDispError` 개체입니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)