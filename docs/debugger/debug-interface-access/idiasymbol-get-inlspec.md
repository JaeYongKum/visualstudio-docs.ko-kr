---
title: IDiaSymbol::get_InlSpec | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_InlSpec method
ms.assetid: 30af6a2f-be84-429e-a96a-d0f9ed9343fb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b82196d2440c3bf5d5c5c24471bc094f8bc5b7b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56638207"
---
# <a name="idiasymbolgetinlspec"></a>IDiaSymbol::get_InlSpec
이 함수는 함수를 인라인으로 표시 여부를 나타내는 플래그를 가져옵니다 (중 하나를 사용 합니다 [__inline 인라인 \__forceinline](/cpp/cpp/inline-functions-cpp) 특성).

## <a name="syntax"></a>구문

```C++
HRESULT get_inlSpec(
   BOOL *pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 `pRetVal`

[out] 반환 `TRUE` 함수를 인라인으로;로 표시 되어 있으면 반환이 고, 그렇지 `FALSE`합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.

> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.

## <a name="requirements"></a>요구 사항

|요구 사항|설명|
|-----------------|-----------------|
|헤더:|dia2.h|
|버전:|DIA SDK v8.0|

## <a name="see-also"></a>참고 항목
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [inline, __inline, \__forceinline](/cpp/cpp/inline-functions-cpp)