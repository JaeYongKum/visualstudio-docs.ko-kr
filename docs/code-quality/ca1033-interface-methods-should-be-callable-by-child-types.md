---
title: 'CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1fd8ee08b53ef3f9216edcb67ebcdbe6c4978bb3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55908714"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 unsealed 형식이 public 인터페이스의 명시적 메서드 구현을 제공하면서 외부에서 볼 수 있는 같은 이름의 대체 메서드를 제공하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 기본 형식을 명시적으로 공용 인터페이스 메서드를 구현 하는 것이 좋습니다. 기본 형식에서 파생 된 형식 상속 된 인터페이스 메서드를 현재 인스턴스에 대 한 참조를 통해서만 액세스할 수 있습니다 (`this` C#) 인터페이스에는 캐스팅 됩니다. 파생된 형식을 다시 상속 된 인터페이스 메서드 구현 (명시적)을 하는 경우 기본 구현은 더 이상 액세스할 수 없습니다. 현재 인스턴스 참조를 통해 호출 파생 된 구현; 호출 그러면, 재귀 및 스택 오버플로가 발생 합니다.

 이 규칙의 명시적 구현에 대 한 위반을 보고 하지 않습니다 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 외부에서 볼 때 `Close()` 또는 `System.IDisposable.Dispose(Boolean)` 메서드가 제공 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하 고, 같은 기능을 노출 하 고 파생된 형식에 표시 되는 새 메서드를 구현 또는 명시적이 아닌 구현으로 변경 합니다. 주요 변경 내용 허용 되는 경우 대 안으로 봉인 된 형식입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 외부에 표시 되는 메서드를 명시적으로 구현 된 메서드 이름이 다른 하지만 같은 기능이 있는 제공할 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 `ViolatingBase`, 규칙을 위반 하는 형식이 있는 `FixedBase`, 보여주는 위반에 대 한 수정 합니다.

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]

## <a name="see-also"></a>참고자료
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)