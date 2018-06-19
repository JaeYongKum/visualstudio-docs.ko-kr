---
title: String.raw 함수 (JavaScript) | Microsoft Docs
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
ms.assetid: b1038b73-3944-4645-b075-3a674b313762
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53df2bf0e455da8b1ccc6de3cbf3f4e3ebee4c09
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24640163"
---
# <a name="stringraw-function-javascript"></a>String.raw 함수(JavaScript)
템플릿 문자열의 원시 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
String.raw`templateStr`;  
String.raw(obj, ...substitutions);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `templateStr`  
 필수 요소. 템플릿 문자열입니다.  
  
 `obj`  
 필수 요소. {raw: 'value'} 등의 개체 리터럴 표기법을 사용하여 지정한 올바른 형식의 개체입니다.  
  
 `...substitutions`  
 선택 사항입니다. 배열 (한 [rest 매개 변수](../../javascript/functions-javascript.md)) 하나 이상의 대체 값으로 구성 된 합니다.  
  
## <a name="remarks"></a>설명  
 `String.raw` 함수를 사용 하기 위한 [템플릿 문자열](../../javascript/advanced/template-strings-javascript.md)합니다. 원시 문자열은 문자열에 있는 모든 이스케이프 문자 및 백슬래시를 포함합니다.  
  
 `obj`가 올바른 형식의 개체가 아닌 경우 오류가 발생합니다.  
  
## <a name="example"></a>예제  
  
```  
function log(arg) {  
    if(console && console.log) {  
        console.log(arg);  
    }  
};  
  
var name = "bob";  
  
log(`hello \t${name}`);  
log(String.raw`hello \t${name}`);  
// The following usage for String.raw is supported but  
// is not typical.  
log(String.raw({ raw: 'fred'}, 'F', 'R', 'E'));  
  
// Output:  
// hello   bob  
// hello \tbob  
// fFrReEd   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]