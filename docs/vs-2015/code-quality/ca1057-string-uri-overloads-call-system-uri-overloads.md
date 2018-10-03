---
title: 'CA1057: 문자열 URI 오버 로드는 System.Uri 오버 로드를 호출할 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1057
- StringUriOverloadsCallSystemUriOverloads
helpviewer_keywords:
- StringUriOverloadsCallSystemUriOverloads
- CA1057
ms.assetid: ef1e983e-9ca7-404b-82d7-65740ba0ce20
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7cb8f559e4290c27c7b241bc15daf6ff79298372
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591203"
---
# <a name="ca1057-string-uri-overloads-call-systemuri-overloads"></a>CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1057: 문자열 URI 오버 로드는 System.Uri 오버 로드를 호출할](https://docs.microsoft.com/visualstudio/code-quality/ca1057-string-uri-overloads-call-system-uri-overloads)합니다.

|||
|-|-|
|TypeName|StringUriOverloadsCallSystemUriOverloads|
|CheckId|CA1057|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식이 선언 된 문자열 매개 변수 대체에 의해서만 달라 지는 메서드 오버 로드는 <xref:System.Uri?displayProperty=fullName> 매개 변수 및 문자열 매개 변수를 사용 하는 오버 로드는 오버 로드를 호출 하지 않습니다는 <xref:System.Uri> 매개 변수입니다.

## <a name="rule-description"></a>규칙 설명
 오버 로드만 다르므로 문자열 /<xref:System.Uri> 매개 변수를 uniform resource identifier (URI)를 나타내는 문자열을 간주 됩니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. <xref:System.Uri> 클래스는 안전 하 고 안전한 방식으로 이러한 서비스를 제공 합니다. 장점을 이용 하는 <xref:System.Uri> 클래스를 문자열 오버 로드를 호출 해야 합니다 <xref:System.Uri> 문자열 인수를 사용 하 여 오버 로드.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 다시의 인스턴스를 만들 수 있도록 URI의 문자열 표현을 사용 하는 메서드를 구현 합니다 <xref:System.Uri> 클래스는 문자열 인수를 사용 하 고 다음 전달를 <xref:System.Uri> 개체에는 오버 로드는 <xref:System.Uri> 매개 변수.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 문자열 매개 변수는 URI를 나타내지 않는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 오버 로드를 올바르게 구현 된 문자열을 보여 줍니다.

 [!code-cpp[FxCop.Design.CallUriOverload#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cpp/FxCop.Design.CallUriOverload.cpp#1)]
 [!code-csharp[FxCop.Design.CallUriOverload#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/cs/FxCop.Design.CallUriOverload.cs#1)]
 [!code-vb[FxCop.Design.CallUriOverload#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CallUriOverload/vb/FxCop.Design.CallUriOverload.vb#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1056: URI 속성은 문자열이면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI 반환 값은 문자열이면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)


