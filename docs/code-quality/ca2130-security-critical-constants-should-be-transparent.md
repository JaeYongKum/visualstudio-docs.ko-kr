---
title: 'CA2130: 보안 위험 상수는 투명해야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0c3ebb69901f031e183d883319861c7e6ef75c2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49858189"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: 보안 위험 상수는 투명해야 합니다.

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 상수 필드 또는 열거형 멤버를 사용 하 여 표시 되어 여 <xref:System.Security.SecurityCriticalAttribute>입니다.

## <a name="rule-description"></a>규칙 설명
 런타임에 조회가 필요하지 않도록 컴파일러에서 상수 값을 인라인하기 때문에 상수 값에 투명성이 적용되지 않습니다. 상수 필드는 보안 투명해야 하므로 코드 검토자는 투명 코드가 상수에 액세스할 수 없다고 가정하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 필드 또는 값에서 SecurityCritical 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 열거형 값 `EnumWithCriticalValues.CriticalEnumValue` 상수의 `CriticalConstant` 이 경고가 발생 합니다. 문제를 해결 하려면 제거를 [`SecurityCritical`] 특성 수 있도록 보안 투명 합니다.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]