---
title: CV_access_e | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c77135fe5ab8e6971bac7cb17d8fa98e5c20577a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986568"
---
# <a name="cvaccesse"></a>CV_access_e
표시 유형 (액세스 수준) 멤버 함수 및 변수의 범위를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>요소  
 CV_private  
 멤버 액세스 가능성은 private입니다.  
  
 CV_protected  
 멤버 액세스를 보호 했습니다.  
  
 CV_public  
 멤버에 대 한 공용 액세스 합니다.  
  
## <a name="remarks"></a>주의  
 `friend` 액세스 지정 자가 포함 되지 않습니다 여기서 클래스의 전용 및 보호 된 요소에 액세스할 수 있는 비 멤버 함수에 의해 일반적으로 사용 됩니다. 사용 된 [idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 메서드를 사용 하 여 기호 찾기 `SymTagFriend` 액세스 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)