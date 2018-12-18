---
title: 'Idiasymbol:: Get_typeids | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bacd3547c1aadfc99b66437acbd73599ec2191f6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942597"
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
이 기호에 대 한 컴파일러 별 형식 식별자 값의 배열을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cTypeIds`  
 [in] 데이터를 저장할 버퍼의 크기입니다.  
  
 `pcTypeIds`  
 [out] 개수를 반환 `typeIds` 기록 또는 `typeIds` 는 `NULL`, 다음 총 형식 식별자를 사용할 수 있습니다.  
  
 `typeIds[]`  
 [out] 배열 형식 식별자로 채워질입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)