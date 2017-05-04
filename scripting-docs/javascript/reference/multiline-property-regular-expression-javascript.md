---
title: "multiline 속성(Regular Expression)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "multiline"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "multiline 속성"
ms.assetid: ca7b276a-1fe2-4189-ac27-f089ab3e9974
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# multiline 속성(Regular Expression)(JavaScript)
정규식에 사용된 multiline 플래그\(**m**\)의 상태를 나타내는 부울 값을 반환합니다.  기본값은 **false**입니다.  읽기 전용입니다.  
  
## 구문  
  
```  
  
rgExp.multiline  
```  
  
## 설명  
 필수 `rgExp` 인수는 `RegExp` 개체의 인스턴스입니다.  
  
 **multiline** 속성은 정규식에 multiline 플래그가 설정되면 **true**를 반환하고, 그렇지 않으면 **false**를 반환합니다.  **m** 플래그로 정규식 개체를 만든 경우 **multiline** 속성은 **true**입니다.  
  
 **multiline**이 **false**이면 "^"은 문자열의 시작 위치와 일치하고 "$"는 문자열의 끝 위치와 일치합니다.  **multline**이 **true**이면 "^"은 "\\n" 또는 "\\r" 다음 위치 및 문자열의 시작 위치와 일치하고 "$"는 문자열의 끝 위치 및 "\\n" 또는 "\\r" 앞 위치와 일치합니다.  
  
## 예제  
 다음 예제에서는 **multiline** 속성의 동작을 보여 줍니다.  아래 표시된 함수에 "m"을 전달하면 단어 "while"이 단어 "and"로 대체됩니다.  이는 multiline 플래그가 설정되었고 줄 바꿈 문자 뒤의 줄 시작 부분에 단어 "while"이 있기 때문입니다.  multiline 플래그를 사용하면 여러 줄 문자열에서 검색을 수행할 수 있습니다.  
  
```javascript  
function RegExpMultilineDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The man hit the ball with the bat ";  
   ss += "\nwhile the fielder caught the ball with the glove.";  
  
   // Replace "while" with "and".  
   var re = new RegExp("^while", flag);  
   var r = ss.replace(re, "and");          
  
   // Output the multiline flag and the resulting string.  
   var s = "";  
   s += "Result for multiline = " + re.multiline.toString();  
   s += ": " + r;  
  
   return(s);  
  
}  
  
sa = RegExpMultilineDemo("m");  
sb = RegExpMultilineDemo("");  
document.write (sa + "<br />" + sb);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## 참고 항목  
 [global 속성\(Regular Expression\)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [ignoreCase 속성\(Regular Expression\)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)