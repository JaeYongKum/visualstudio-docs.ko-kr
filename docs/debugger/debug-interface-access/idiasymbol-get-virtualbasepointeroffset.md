---
title: 'Idiasymbol:: Get_virtualbasepointeroffset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualBasePointerOffset method
ms.assetid: a4f2649c-6702-491c-90a1-d6d669258c51
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 17fda4a74c1497d48baea1d9e1a817b4b12cf344
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49898955"
---
# <a name="idiasymbolgetvirtualbasepointeroffset"></a>IDiaSymbol::get_virtualBasePointerOffset
가상 기본 포인터의 오프셋을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_virtualBasePointerOffset (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 가상 기본 포인터의 오프셋을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)