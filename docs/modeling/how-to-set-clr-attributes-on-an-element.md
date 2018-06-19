---
title: '방법: 요소에 CLR 특성 설정'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ceca2556e269d554d40e025e5edcb91753149622
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948914"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>방법: 요소에 CLR 특성 설정
사용자 지정 특성은 도메인 요소, 셰이프, 커넥터 및 다이어그램에 추가할 수 있는 특수 한 특성입니다. 상속 되는 모든 특성을 추가할 수는 `System.Attribute` 클래스입니다.

### <a name="to-add-a-custom-attribute"></a>사용자 지정 특성을 추가 하려면

1.  에 **DSL 탐색기**, 사용자 지정 특성을 추가 하려면 원하는 요소를 선택 합니다.

2.  에 **속성** 창, 옆에는 **사용자 지정 특성** 속성을 찾아보기 (**...** ) 아이콘입니다.

     **특성 편집** 대화 상자가 열립니다.

3.  에 **이름** 열을 클릭 하 여  **\<특성을 추가 >** 특성의 이름을 입력 합니다. Enter 키를 누릅니다.

4.  특성 이름 아래에 선이 괄호를 보여 줍니다. 이 줄에 입력 특성에 대 한 매개 변수 형식 (예를 들어 `string`), 한 다음 ENTER 키를 누릅니다.

5.  에 **Name 속성** 열을 적절 한 이름, 예를 들어 입력 `MyString`합니다.

6.  **확인**을 클릭합니다.

     **사용자 정의 특성** 속성 이제 다음과 같은 형식의 특성을 표시 합니다.

     `[` *AttributeName* `(` *ParameterName* `=` *유형* `)]`

## <a name="see-also"></a>참고 항목

- [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)