---
title: 'CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4462bb8ef65fdf593ab0bf64813c19af5d390d97
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55916819"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.

|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인

투명 메서드:

- 보안에 중요 한 보안 예외 형식을 처리합니다.

- 보안 중요 한 형식으로 표시 된 매개 변수가

- 보안 중요 한 제약 조건이 있는 제네릭 매개 변수

- 보안 중요 형식의 지역 변수가 있습니다.

- 로 표시 된 보안 중요 형식을 참조 합니다.

- 중요 한 보안으로 표시 된 메서드를 호출

- 중요 한 보안으로 표시 된 필드 참조

- 중요 한 보안으로 표시 된 형식을 반환합니다

## <a name="rule-description"></a>규칙 설명

로 표시 된 코드 요소를 <xref:System.Security.SecurityCriticalAttribute> 특성이 보안에 중요 합니다. 투명 메서드는 보안에 중요한 요소를 사용할 수 없습니다. 투명 형식이 보안에 중요 한 형식을 사용 하려고 하는 경우는 <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , 또는 <xref:System.FieldAccessException> 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 다음 중 하나를 수행 합니다.

- 사용 하 여 중요 한 보안 코드를 사용 하는 코드 요소를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 특성

     \- 또는 -

- 제거 합니다 <xref:System.Security.SecurityCriticalAttribute> 중요 한 보안으로 표시 되 고 대신 사용 하 여 표시 된 코드 요소가 특성을 <xref:System.Security.SecuritySafeCriticalAttribute> 또는 <xref:System.Security.SecurityTransparentAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 투명 메서드는 보안에 중요 한 제네릭 컬렉션, 보안 중요 한 필드 및 보안 중요 메서드를 참조 하려고 합니다.

[!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]

## <a name="see-also"></a>참고자료

- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityCriticalAttribute>
- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityTreatAsSafeAttribute>
- <xref:System.Security?displayProperty=fullName>