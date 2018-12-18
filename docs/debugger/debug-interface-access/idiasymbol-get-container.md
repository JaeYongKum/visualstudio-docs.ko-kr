---
title: 'Idiasymbol:: Get_container | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d293971cfcd0723485d4a5b21d4e431de64ddd65
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822737"
---
# <a name="idiasymbolgetcontainer"></a>IDiaSymbol::get_container
이 함수는이 기호의 부모/컨테이너를 나타내는 기호에 대 한 포인터를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 에 대 한 포인터를 반환 합니다.는 `IDiaSymbol` 이 기호의 컨테이너에 대 한 정보를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 S_FALSE 또는 오류 코드를 반환합니다.  
  
> [!NOTE]
>  S_FALSE 반환 값 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)