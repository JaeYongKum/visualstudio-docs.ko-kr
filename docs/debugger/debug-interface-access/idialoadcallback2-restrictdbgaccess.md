---
title: IDiaLoadCallback2::RestrictDBGAccess | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictDBGAccess method
ms.assetid: 63b67a93-2910-4fff-aa70-6b2eaa08e5c8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 24317ff7a79815e5af2306b09cc8d2aa3bfdde0d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56595855"
---
# <a name="idialoadcallback2restrictdbgaccess"></a>IDiaLoadCallback2::RestrictDBGAccess
.Dbg 파일에서 디버그 정보를 찾고 허용 되는지 여부를 결정 합니다.

## <a name="syntax"></a>구문

```C++
HRESULT RestrictDBGAccess();
```

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>주의
 이외의 다른 모든 반환 값 `S_OK` .dbg 파일에서 디버그 정보를 찾으시나요 방지 하기 위해.

## <a name="see-also"></a>참고 항목
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)