---
title: 'CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2ed7249925f066cdbba7616b368e80e7b8126bca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54936006"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식을 구현 하는 형식에서 파생 되는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 사용 하 고 다음 조건 중 하나는 true.

- 형식에서 사용 하는 생성자, 즉 serialization 생성자를 구현 하는 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 매개 변수 서명 하지만 기본 형식의 serialization 생성자를 호출 하지 않습니다.

- 형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드를 호출 하지 않습니다 하지만 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 기본 형식의 메서드.

## <a name="rule-description"></a>규칙 설명
 사용자 지정 serialization 프로세스에서 형식이 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 해당 필드와 필드를 serialization 생성자를 serialize 하는 방법입니다. 형식을 구현 하는 형식에서 파생 되는 경우는 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 기본 형식 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 및 serialization 생성자를 호출 해야 serialize serialize/de-serialize 하는 기본 형식의 필드입니다. 이 고, 그렇지 형식 없습니다 직렬화 되며 올바르게 역직렬화 합니다. 파생된 형식에서 모든 새 필드를 추가 하지 않습니다, 경우 형식 필요는 없습니다 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드나 serialization 생성자 또는 해당 하는 기본 형식 요소를 호출 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 기본 형식을 호출 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드나 serialization 생성자를 해당 형식의 메서드나 생성자를 파생 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 serialization 생성자를 호출 하 여 규칙을 충족 하는 파생된 형식 및 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드의 기본 클래스입니다.

 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>관련된 규칙
 [CA2240: ISerializable을 올바르게 구현](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: 모든 순차 불가능 필드를 표시 합니다.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: 선택적 필드에 deserialization 메서드를 제공 합니다.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)