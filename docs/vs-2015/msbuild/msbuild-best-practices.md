---
title: MSBuild 모범 사례 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ad2070bb696a3ce326331d01145b3ef3b54ae5ec
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54780668"
---
# <a name="msbuild-best-practices"></a>MSBuild 모범 사례
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
MSBuild 스크립트를 작성할 때는 다음 모범 사례를 따르는 것이 좋습니다.  
  
-   기본 속성 값은 명령줄에서 기본값을 재정의할 수 있는 속성을 선언하는 대신 `Condition` 특성을 사용하여 처리하는 것이 가장 효율적입니다. 예를 들어 다음과 같은 코드를 사용합니다.  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   항목을 선택할 때는 와일드카드를 사용하지 않습니다. 대신 파일을 명시적으로 지정합니다. 이렇게 하면 파일을 추가하거나 삭제할 때 발생할 수 있는 오류를 보다 쉽게 추적할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 개념](../msbuild/msbuild-advanced-concepts.md)
