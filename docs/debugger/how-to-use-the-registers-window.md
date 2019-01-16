---
title: 디버거에서 레지스터 값 보기 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/19/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8622bb1288324429ad346834930559d1435ac6d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867581"
---
# <a name="view-register-values-in-the-registers-window-c-c-visual-basic-f"></a>레지스터 창에서 레지스터 값 보기 (C#, c + +, Visual Basic의 경우 F#)

합니다 **등록** 레지스터 내용이 Visual Studio에서 디버깅 하는 동안 창이 표시 됩니다. 간략 한 소개 레지스터 개념에 대 한 하며 **레지스터** 창 참조 [디버깅 기본 사항: 레지스터 창](../debugger/debugging-basics-registers-window.md).

> [!NOTE]
> 등록 정보 스크립트나 SQL 응용 프로그램에 사용할 수 없는 경우

디버그 하는 동안 앱에서 코드 실행 값을 등록 합니다. 변경 된 값은 최근에에서 빨간색으로 표시 합니다 **등록** 창입니다.

**레지스터** 창에서는 레지스터를 플랫폼 및 프로세서 유형에 따라 각각 다른 그룹으로 구성하여 간단하게 표시합니다. 표시 하거나 레지스터 그룹을 숨길 수 있습니다. 자세한 내용은 [방법: 레지스터 그룹 표시 및 숨기기](../debugger/how-to-display-and-hide-register-groups.md)를 참조하세요.

레지스터 값은 편집할 수 있습니다. 자세한 내용은 [방법: 레지스터 값 편집](../debugger/how-to-edit-a-register-value.md)을 참조하세요.

**레지스터 창을 열려면**

1. 선택 하 여 주소 수준 디버깅 사용 **주소 수준 디버깅을 활성화** 에 **도구** (또는 **디버그**) > **옵션**  >  **디버깅**합니다.

1. 실행 중이거나 중단점은 디버깅, 선택 **디버그** > **Windows** > **등록**를 누르거나 **Alt** + **5**합니다.

>[!NOTE]
>대화 상자와 메뉴 명령은 설정 또는 Visual Studio 버전에 따라 달라질 수 있습니다. 설정을 변경 하려면 선택 **설정 가져오기 및 내보내기** Visual studio **도구** 메뉴. 자세한 내용은 [재설정 설정](../ide/environment-settings.md#reset-settings)을 참조하세요.

### <a name="see-also"></a>참고 항목

- [디버깅 기본 사항: 레지스터 창](../debugger/debugging-basics-registers-window.md)
- [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)
