---
title: toLocaleString (Number) | Microsoft Docs
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
ms.assetid: 42c05252-13c1-4943-b1a4-b33285aeab3e
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b5e6378ec94e032c908a3502c0324c2a5a91b26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24640833"
---
# <a name="tolocalestring-number"></a>toLocaleString(Number)
현재 또는 지정 된 로캘을 사용 하 여 번호를 문자열로 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
numberObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>매개 변수  
 `numberObj`  
 필수 요소. `Number` 변환할 개체입니다.  
  
 `locales`  
 선택 사항입니다. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  
  
 `options`  
 선택 사항입니다. 비교 옵션을 지정하는 하나 이상의 속성이 포함된 개체입니다.  
  
## <a name="remarks"></a>설명  
 Internet Explorer 11부터 `toLocaleString` 사용 하 여 `Intl.NumberFormat` 확인 비교에 대 한 지원을 추가 하는 내부적으로 `locales` 및 `options` 매개 변수입니다. 이러한 매개 변수에 대 한 자세한 내용은 참조 [Intl.NumberFormat](../../javascript/reference/intl-numberformat-object-javascript.md)합니다.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 일부 문서 모드 및 브라우저 버전에서는 지원되지 않습니다. 자세한 내용은 요구 사항 섹션을 참조하세요.  
  
> [!NOTE]
>  생략 하면는 `locales` 매개 변수를 사용 하 여 `toLocaleString` ; 사용자에 게 결과 표시할에 사용 하 여 스크립트 내에서 값을 계산 하므로 반환 된 결과 컴퓨터 별로 (메서드는 현재 로캘을 반환 하는 데 사용).  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `toLocaleString` 매개 변수 없이 메서드.  
  
```JavaScript  
var n, s;  
n = new Number(100);  
s = "Current locale value is: ";  
s += n.toLocaleString();                 
document.write(s);  
  
// Output:  
// The value 100 as represented by the current locale.  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 지정된 로캘 및 비교 옵션과 함께 `toLocaleString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
document.write(number.toLocaleString("en-US"));  
// 123,456,789  
document.write(number.toLocaleString("ja-JP"));  
// 123,456,789  
document.write(number.toLocaleString("ar-SA", options1));  
// ١٢,٣٤٥,٦٧٨,٩٠٠ %  
document.write(number.toLocaleString("hi-IN", options2));  
// ₹ 12,34,56,789.00  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleDateString 메서드(Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)