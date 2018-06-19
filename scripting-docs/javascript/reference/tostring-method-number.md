---
title: toString 메서드 (Number) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 07c3484b-d9d8-4451-a2be-88a19a081966
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6be170061faf4c2782c7247c80c55065c3a6742
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24640393"
---
# <a name="tostring-method-number"></a>toString 메서드(Number)
숫자의 문자열 표현을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
number.toString()  
```  
  
## <a name="parameters"></a>매개 변수  
 `number`  
 필수 요소. 나타내는 문자열로 서 수입니다.  
  
## <a name="return-value"></a>반환 값  
 숫자의 문자열 표현입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **toString** 숫자로 메서드.  
  
```JavaScript  
var number = 234.567;  
var s = number.toString();  
document.write(s.length);  
  
// Output: 7  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]