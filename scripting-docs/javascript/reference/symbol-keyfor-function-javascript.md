---
title: Symbol.keyFor 함수 (JavaScript) | Microsoft Docs
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
ms.assetid: f0b6f034-6d0a-421c-b1c6-52489411e9a3
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 22f671a1ea14ce56c52fccbce75893516a10bcc5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24639533"
---
# <a name="symbolkeyfor-function-javascript"></a>Symbol.keyFor 함수(JavaScript)
지정된 기호에 대한 키를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Symbol.keyFor(sym);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `sym`  
 필수 요소. 기호 개체입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 전체 기호 레지스트리에서 해당 기호를 검색합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Local symbol  
var sym1 = Symbol("desc");  
// Global symbol  
var sym2 = Symbol.for("desc");  
  
console.log(Symbol.keyFor(sym1)):  
console.log(Symbol.keyFor(sym2));  
  
// Output:  
// undefined  
// desc  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]