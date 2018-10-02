---
title: 'CA1725: 매개 변수 이름은 기본 선언과 일치 해야 | Microsoft Docs'
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
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 20a7e5f0239d572ec1867ffdac80f116cfd8360a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591963"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1725: 매개 변수 이름은 기본 선언과 일치 해야](https://docs.microsoft.com/visualstudio/code-quality/ca1725-parameter-names-should-match-base-declaration)합니다.

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에서 표시 되는 메서드 재정의에서 매개 변수의 이름을 메서드의 기본 선언이 나 메서드의 인터페이스 선언에서 매개 변수의 이름을 매개 변수의 이름이 일치 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 재정의 계층 구조에서 매개 변수 이름을 일관되게 지정하면 메서드 재정의를 더 편리하게 사용할 수 있습니다. 파생된 메서드의 매개 변수 이름이 기본 선언의 이름과 다르면 메서드가 기본 메서드의 재정의인지 메서드의 새 오버로드인지를 혼동할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 기본 선언과 일치 하도록 매개 변수를 이름을 바꿉니다. 수정 프로그램은 COM 볼 수 있는 메서드에 대 한 주요 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이전에 제공 된 라이브러리에 COM 노출 메서드를 제외 하 고이 규칙에서 경고를 표시 하지 마십시오.



