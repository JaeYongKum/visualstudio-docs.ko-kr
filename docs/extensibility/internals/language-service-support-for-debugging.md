---
title: 디버깅에 대 한 언어 서비스 지원 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 18856d2f3a6359a3be019e4e97e63832e896c2a9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604745"
---
# <a name="language-service-support-for-debugging"></a>디버깅에 대한 언어 서비스 지원
언어 서비스를 통해 디버거를 지 원하는 기능을 제공할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> 인터페이스입니다. 이러한 기능은 다음 중단점 유효성 검사 및 식의 목록을 제공 합니다 **자동** 창입니다.

 그러나 언어를 디버그 하는 식 계산기가 해야 합니다. 식 계산기는 디버깅 하는 동안 값을 생성 하는 식을 계산 하는 일을 담당 합니다. CLR 식 계산기를 구현 하는 방법에 대 한 내용은 다음을 참조 하세요.

-   [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)

-   [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)

## <a name="compiler-output"></a>컴파일러 출력
 컴파일러의 형식 언어에 대 한 디버깅을 구현 하기 위해 수행 해야 하는 항목을 결정 합니다. 컴파일러는 Windows 운영 체제를 대상으로 하 고.pdb 파일을 작성 하는 경우 네이티브 코드 디버깅 Visual Studio에 통합 된 엔진을 사용 하 여 프로그램을 디버깅할 수 있습니다. 컴파일러는 MSIL (Microsoft intermediate language)를 생성 하는 경우에 디버깅 엔진으로, Visual Studio에도 통합 되어 관리 되는 코드를 사용 하 여 프로그램을 디버깅할 수 있습니다. 컴파일러는 전용 운영 체제 또는 다양 한 런타임 환경을 대상으로 하는 경우 디버깅 엔진을 직접 작성 해야 합니다.

 언어에 대 한 디버깅 구현에 대 한 자세한 내용은 참조 하세요. [Getting Started](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) Visual Studio 디버깅 sdk에서.