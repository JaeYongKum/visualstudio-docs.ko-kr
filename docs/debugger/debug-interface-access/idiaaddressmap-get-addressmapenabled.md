---
title: 'Idiaaddressmap:: Get_addressmapenabled | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::get_addressMapEnabled method
ms.assetid: 6183dc5e-befa-4e5a-ae5a-f4aa24f3ed9e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7391010e409cc25a3151bb2abb806289c81288a1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641884"
---
# <a name="idiaaddressmapgetaddressmapenabled"></a>IDiaAddressMap::get_addressMapEnabled
주소 지도 특정 세션에 대해 설정 되었는지 여부를 나타냅니다.

## <a name="syntax"></a>구문

```C++
HRESULT get_addressMapEnabled ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>매개 변수
 pRetVal

[out] 반환 `TRUE` 주소 매핑을 사용 하는 경우.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>주의
 경우에 따라 실행 후 프로세서 실행 파일을 업데이트합니다. DIA 기호 새 레이아웃의 번역 지원 하도록 메커니즘을 포함 합니다.

 클라이언트 응용 프로그램 특정 세션을 가져옴으로써에 매핑된 주소를 설정할 수는 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md) 에서 인터페이스를 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 인터페이스를 호출 합니다 [IDiaAddressMap::set_ addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드를 호출 하 여 여러 번 합니다 [idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) 메서드. 합니다 `get_addressMapEnabled` 메서드 호출의 결과 반환 합니다 `put_addressMapEnabled` 메서드.

## <a name="see-also"></a>참고 항목
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)