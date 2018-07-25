---
title: 사용자 환경 개선 프로그램
description: Visual Studio에서 개인 정보 설정을 관리하는 방법을 알아봅니다.
ms.date: 05/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba68d0d369d178606777944c9dc4dcd633a503f4
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280646"
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Visual Studio 사용자 환경 개선 프로그램

VSCEIP(Visual Studio 사용자 환경 개선 프로그램)는 Microsoft가 시간이 지남에 따라 Visual Studio를 개선하는 데 도움이 되도록 설계되었습니다. 이 프로그램은 컴퓨터에서 사용자의 작업을 방해하지 않고 [오류](../ide/diagnostic-data-collection.md), 컴퓨터 하드웨어 및 사용자가 Visual Studio를 사용하는 방법에 대한 정보를 수집합니다. 수집되는 정보는 Microsoft가 개선할 기능을 식별하는 데 도움이 됩니다. 이 문서에서는 VSCEIP를 옵트인하거나 옵트아웃하는 방법에 대해 설명합니다.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

## <a name="opt-in-or-out"></a>옵트인 또는 옵트아웃

VSCEIP는 기본적으로 켜져 있습니다. 다음 지침을 따라 이 기능을 끄거나 다시 켤 수 있습니다.

1. Visual Studio를 시작합니다.

1. **도움말** 메뉴에서 **피드백 보내기**를 가리킨 다음, **설정**을 선택합니다.

   **Visual Studio 환경 개선 프로그램** 대화 상자가 열립니다.

1. 옵트아웃하려면 **아니요, 참여하지 않겠습니다**를 선택한 다음, **확인**을 선택합니다.
   옵트인하려면 **예, 참여하겠습니다**를 선택한 다음, **확인**을 선택합니다.

   ![Visual Studio 환경 개선 프로그램 대화 상자](media/experience-improvement-program.png)

### <a name="registry-settings"></a>레지스트리 설정

[Visual Studio용 빌드 도구](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017)를 설치하는 경우, VSCEIP를 구성하도록 레지스트리를 업데이트해야 합니다. Enterprise 고객은 레지스트리 기반 정책을 설정하여 VSCEIP를 옵트인하거나 옵트아웃하는 그룹 정책을 구성할 수 있습니다.

관련 레지스트리 키와 설정은 다음과 같습니다.

64비트 OS에서 Key = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\15.0\SQM** 32비트 OS에서 Key = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\15.0\SQM** 그룹 정책을 사용하는 경우 Key = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM**

항목 = **OptIn**

값 = (DWORD)
- **0**은 옵트아웃된 것입니다(VSCEIP 끄기).
- **1**은 옵트인된 것입니다(VSCEIP 켜기).

> [!CAUTION]
> 레지스트리를 잘못 편집하면 시스템이 심각하게 손상될 수 있습니다. 레지스트리를 변경하기 전에 컴퓨터의 중요한 데이터를 모두 백업해야 합니다. 변경 내용을 수동으로 적용한 후 문제가 발생할 경우 **마지막으로 성공한 구성** 시작 옵션을 사용할 수도 있습니다.

VSCEIP를 통해 수집, 처리 또는 전송되는 정보에 대한 자세한 내용은 [Microsoft 개인정보처리방침](https://privacy.microsoft.com/privacystatement)을 참조하세요.

## <a name="see-also"></a>참고 항목

* [Visual Studio에서 수집한 진단 정보](diagnostic-data-collection.md)
* [의견 보내기](../ide/talk-to-us.md)
* [Visual Studio의 문제를 보고하는 방법](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)
* [Microsoft 개인정보처리방침](https://privacy.microsoft.com/privacystatement)
