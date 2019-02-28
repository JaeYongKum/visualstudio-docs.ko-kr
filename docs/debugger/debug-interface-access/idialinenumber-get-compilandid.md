---
title: 'Idialinenumber:: Get_compilandid | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_compilandId method
ms.assetid: 2cd6f551-8091-47c7-803f-3f79a766a211
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9874dec57c873164ec1875f31fd15c817781bb7a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56610916"
---
# <a name="idialinenumbergetcompilandid"></a>IDiaLineNumber::get_compilandId
이 줄을 제공한 컴파일 대상에 대 한 고유 식별자를 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_compilandId ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 반환 `DWORD` 이 줄을 제공한 컴파일 대상에 대 한 고유 식별자를 포함 하는 합니다.

## <a name="return-value"></a>반환 값
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="see-also"></a>참고 항목
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)