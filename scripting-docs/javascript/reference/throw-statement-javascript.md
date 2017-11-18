---
title: "throw 문 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: throw_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error handling, throw statement
- throw statement
ms.assetid: 75cbade0-fb81-4ffe-b187-b71be380bb05
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cedecec1c5f13e1aba07273c1e3deca4f835429
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="throw-statement-javascript"></a>throw 문(JavaScript)
처리 될 수 있는 오류 조건을 생성 한 `try...catch...finally` 문.  
  
## <a name="syntax"></a>구문  
  
```  
throw exception   
```  
  
## <a name="remarks"></a>설명  
 필요한 `exception` 인수 식일 수 있습니다.  
  
 다음 예제에서 내부 오류가 발생 한 `try` 하며 블록에 들어갈는 `catch` 블록입니다.  
  
```JavaScript  
try {  
        throw new Error(200, "x equals zero");  
}  
catch (e) {  
    document.write(e.message);  
}  
  
// Output: x equals zero.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [try … catch 마지막 문...](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error 개체](../../javascript/reference/error-object-javascript.md)