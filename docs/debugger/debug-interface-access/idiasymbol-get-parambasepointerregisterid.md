---
title: 'Idiasymbol:: Get_parambasepointerregisterid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_paramBasePointerRegisterId method
ms.assetid: 9f5caeb4-5c88-4054-bf8b-50d34bbbf8c5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b74250c453f42b4591bb87ef0a281d74de3b489
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49852884"
---
# <a name="idiasymbolgetparambasepointerregisterid"></a>IDiaSymbol::get_paramBasePointerRegisterId
매개 변수에 기본 포인터를 보유 하는 레지스터의 ID를 검색 합니다. 사용 시기를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 로 설정 된 `SymTagFunction`합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_paramBasePointerRegisterId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 매개 변수에 기본 포인터를 보유 하는 레지스터의 ID를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)