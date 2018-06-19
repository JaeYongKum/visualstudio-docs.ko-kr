---
title: 관리 코드에 대 한 설정 관리 최소 규칙 규칙
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 9803c5171cb15454e465253e410b3dc2f4e6215e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919054"
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>관리 코드에 대 한 설정 관리 최소 규칙 규칙
관리 최소 규칙은 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요 한 논리 및 디자인 오류를 비롯 하 여 코드의 가장 중요 한 문제에 집중 합니다. 프로젝트에 대해 만드는이 규칙 사용자 지정 규칙 집합에 있는 집합을 포함 해야 합니다.

|규칙|설명|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|빈 종료자를 제거하십시오.|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|삭제 가능한 필드는 삭제해야 합니다.|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.|
