---
title: 'Idiasymbol:: Get_indirectvirtualbaseclass | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_indirectVirtualBaseClass method
ms.assetid: 853b5c6f-e1cb-4675-ad36-9ee16e3341c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e4912fd4ec9280b1ee429ea52bf1a06cac636aac
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611063"
---
# <a name="idiasymbolgetindirectvirtualbaseclass"></a>IDiaSymbol::get_indirectVirtualBaseClass
사용자 정의 데이터 형식에는 간접 가상 기본 클래스 인지 여부를 지정 하는 플래그를 검색 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_indirectVirtualBaseClass ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 반환 `TRUE` 사용자 정의 데이터 형식이 간접 가상 기본 클래스입니다; 그렇지 않으면 반환 `FALSE`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v7.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)