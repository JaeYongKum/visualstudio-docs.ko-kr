---
title: 'Idiaenuminjectedsources:: Item | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d258e2c1ba71ab294435f2437c7b6dc3de75cfb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925791"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
인덱스를 사용 하 여 삽입 된 소스를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaInjectedSource** injectedSource  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 인덱스입니다.  
 [in] 인덱스를 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 검색 된 개체입니다. 인덱스는 0에서 범위 `count`-1로, 여기서 `count` 에서 반환 되는 [idiaenuminjectedsources:: Get_count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) 메서드.  
  
 injectedSource  
 [out] 반환 된 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 삽입 된 소스를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)