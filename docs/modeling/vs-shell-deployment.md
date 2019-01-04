---
title: VS 셸 배포
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 2d732b050a9f12b6324abaf253739cd4f3e223aa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53914490"
---
# <a name="vs-shell-deployment"></a>VS 셸 배포

Visual Studio를 확인할 수는 격리 된 셸 있습니다 도메인 특정 언어 및 해당 솔루션 표시 방법을 상호 작용 해야 하는 기능입니다. Visual Studio 격리 셸에 대 한 자세한 내용은 참조 하세요. [격리 셸 사용자 지정](https://vspartner.com/pages/vsshells)합니다.

배포 대상으로는 Visual Studio Shell을 설정 합니다.

1. 에 **DslPackage** 프로젝트를 열고 **source.extension.tt**합니다.

2. 아래 `<SupportedProducts>` 삽입:

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   바꿉니다 *MyIsolatedShell* 격리 셸 패키지의 이름입니다.