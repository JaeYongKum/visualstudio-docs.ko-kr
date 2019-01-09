---
title: IObjectIdentity::IsEqualObject | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IObjectIdentity.IsEqualObject
apilocation:
- scrobj.dll
helpviewer_keywords:
- IsEqualObject method
ms.assetid: 78c5c5c2-d299-4036-986c-7c1d87cbe7cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa233e478c83b723b13d19d27dc4b63ee4700bb5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095058"
---
# <a name="iobjectidentityisequalobject"></a>IObjectIdentity::IsEqualObject
개체는 현재 개체와 같은지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT IsEqualObject(  
  IUnknown*punk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `punk`  
 [in] 현재 개체와 비교할 개체의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|개체가 동일 합니다.|  
|`S_FALSE`|개체가 다릅니다.|  
  
## <a name="remarks"></a>설명  
 구현의 합니다 `IsEqualObject` 메서드는 반환 해야 `S_OK` 개체가 동일한 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IObjectIdentity 인터페이스](../../winscript/reference/iobjectidentity-interface.md)