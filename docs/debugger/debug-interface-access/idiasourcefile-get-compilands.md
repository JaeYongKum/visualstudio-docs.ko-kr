---
title: 'Idiasourcefile:: Get_compilands | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_compilands method
ms.assetid: 57deb50a-9c22-43ea-a80c-eab205997bc4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4c97f7e16f193d70048f3803ff764b0bfcdbc69
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49885683"
---
# <a name="idiasourcefilegetcompilands"></a>IDiaSourceFile::get_compilands
이 파일을 참조 하는 줄 번호를가지고 있는 컴파일 대상의 열거자를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_compilands (   
   IDiaEnumSymbols** ppRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppRetVal`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 이 파일을 참조 하는 줄 번호를가지고 있는 모든 컴파일 대상의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)