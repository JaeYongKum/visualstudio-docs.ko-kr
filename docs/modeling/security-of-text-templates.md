---
title: 텍스트 템플릿 보안
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 71052a0d4120a74269f2aa05412230284271e574
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947523"
---
# <a name="security-of-text-templates"></a>텍스트 템플릿 보안
텍스트 템플릿은 다음과 같은 보안 문제가 있습니다.

-   텍스트 템플릿은 임의의 코드가 삽입에 취약 합니다.

-   지시문 프로세서를 찾는 데 사용 하는 호스트 하는 메커니즘이 안전 하지 않은 경우에 악의적인 지시문 프로세서를 실행할 수 있습니다.

## <a name="arbitrary-code"></a>임의의 코드
 서식 파일을 작성할 때 내의 모든 코드를 넣을 수 있습니다는 \<# # > 태그가 있습니다. 따라서 임의의 코드를 텍스트 템플릿 내에서 실행할 수 있습니다.

 신뢰할 수 있는 원본에서 서식 파일을 가져올 해야 합니다. 신뢰할 수 있는 출처에서 제공 하지 않는 템플릿을 실행 하지 않도록 응용 프로그램의 최종 사용자에 게 경고 해야 합니다.

## <a name="malicious-directive-processor"></a>악의적인 지시문 프로세서
 텍스트 템플릿 엔진 변환 호스트 및 하나 이상의 지시문 프로세서를 변환 출력 파일에 템플릿 텍스트와 상호 작용 합니다. 자세한 내용은 참조 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)합니다.

 지시문 프로세서를 찾는 데 사용 하는 호스트 하는 메커니즘 안전 하지 않으면 악의적인 지시문 프로세서 실행의 위험을 실행 됩니다. 악의적인 지시문 프로세서에서 실행 되는 코드를 제공할 수 `FullTrust` 모드는 템플릿이 실행 될 때입니다. 사용자 지정 텍스트 템플릿 변환 호스트를 만드는 경우 지시문 프로세서를 찾도록 엔진에 대 한 레지스트리와 같은 보안 메커니즘을 사용 해야 합니다.