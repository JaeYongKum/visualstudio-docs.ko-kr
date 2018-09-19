---
title: Visual Studio의 오프라인 설치 만들기
description: 불안정한 인터넷 연결 또는 낮은 대역폭이 있는 경우 Visual Studio를 오프라인으로 설치하는 방법에 알아봅니다.
ms.custom: ''
ms.date: 08/28/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 987584be6d2d0a2ee794622e64e989de9ea80334
ms.sourcegitcommit: b9a32c3d94b19e7344f4872bc026efd3157cf220
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46135580"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017의 오프라인 설치 만들기

Visual Studio 2017은 다양한 네트워크 및 컴퓨터 구성에서 제대로 작동하도록 설계되었습니다. 가능한 한 [Visual Studio 웹 설치 관리자](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)를 사용하는 것이 좋습니다. &mdash;이 파일은 작은 파일이며 최신 수정 사항 및 기능을 최신 상태로 유지할 수 있습니다&mdash;.

예를 들어, 불안정한 인터넷 연결이나 대역폭이 낮을 수 있습니다. 이 경우 새로운 "모두 다운로드한 후 설치" 기능을 사용하여 설치하기 전에 파일을 다운로드하거나 명령줄을 사용하여 파일의 로컬 캐시를 만드는 몇 가지 옵션이 있습니다.

> [!NOTE]
> 인터넷에서 방화벽이 사용되는 클라이언트 워크스테이션의 네트워크에 대해 Visual Studio 2017의 배포를 수행하려고 하는 엔터프라이즈 관리자인 경우 [Visual Studio 2017의 네트워크 설치 만들기](../install/create-a-network-installation-of-visual-studio.md) 및 [Visual Studio 오프라인 설치에 필요한 인증서 설치](../install/install-certificates-for-visual-studio-offline.md) 페이지를 참조하세요.

## <a name="use-the-download-all-then-install-feature"></a>"모두 다운로드한 후 설치" 기능 사용

[**15.8의 새로운 기능**](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default&view=vs-2017#install
): 웹 설치 관리자를 다운로드한 후 Visual Studio에서 새로운 **모두 다운로드한 후 설치** 옵션을 선택합니다. 그런 다음, 설치를 계속합니다.

   !["모두 다운로드한 후 설치" 옵션](media/download-all-then-install.png)

## <a name="use-the-command-line-to-create-a-local-cache"></a>명령줄을 사용하여 로컬 캐시 만들기

작은 부트스트래퍼를 다운로드한 후 명령줄을 사용하여 로컬 캐시를 만듭니다. 그런 다음, 로컬 캐시를 사용하여 Visual Studio를 설치합니다. (이 프로세스는 이전 버전에서 사용 가능한 ISO 파일을 대체합니다.)

방법은 다음과 같습니다.

### <a name="step-1---download-the-visual-studio-bootstrapper"></a>1단계 - Visual Studio 부트스트래퍼 다운로드

이 단계를 완료하려면 인터넷 연결이 있어야 합니다.

먼저 선택한 Visual Studio 버전에 대한 Visual Studio 부트스트래퍼를 다운로드합니다. 설치 파일&mdash;또는 부트스트래퍼&mdash;는 다음 중 하나와 일치하거나 비슷합니다.

| 버전                    | 파일                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio 커뮤니티    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

### <a name="step-2---create-a-local-install-cache"></a>2다계 - 로컬 설치 캐시 만들기

이 단계를 완료하려면 인터넷 연결이 있어야 합니다.

명령 프롬프트를 열고 다음 예제의 명령 중 하나를 사용합니다. 여기에 나열된 예제에서는 Visual Studio의 Community Edition을 사용한다고 가정합니다. 사용 중인 버전에 맞게 명령을 조정하세요.

- .NET 웹 및 .NET 데스크톱 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- .NET 데스크톱 및 Office 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- C++ 데스크톱 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- 모든 기능이 포함된 전체 로컬 레이아웃을 만들려면(&mdash;_수많은_ 기능이 있어서 오래 걸릴 수 있음) 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

영어 이외의 언어를 설치하려면 [언어 로케일 목록](#list-of-language-locales)에서 `en-US`를 로캘로 변경합니다. 그런 다음, [사용 가능한 구성 요소 및 워크로드 목록](workload-and-component-ids.md)을 사용하여 설치 캐시를 추가로 사용자 지정합니다.

> [!IMPORTANT]
> 전체 Visual Studio 2017 레이아웃에는 35GB 이상의 디스크 공간이 필요하며 다운로드하는 데 다소 시간이 걸릴 수 있습니다. 설치하려는 구성 요소로만 레이아웃을 만드는 방법에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)를 참조하세요.

### <a name="step-3---install-visual-studio-from-the-local-cache"></a>3단계 - 로컬 캐시에서 Visual Studio 설치

> [!TIP]
> 로컬 설치 캐시에서 실행할 경우 설치 시 이러한 각 파일의 로컬 버전을 사용하게 됩니다. 하지만 설치 중에 캐시에 없는 구성 요소를 선택하면 설치 프로그램은 인터넷에서 해당 구성 요소를 다운로드하려고 시도합니다.

이전에 다운로드한 파일만 설치하려면 레이아웃 캐시를 만드는 데 사용한 것과 동일한 명령줄 옵션을 사용하세요. 예를 들어 다음 명령으로 레이아웃 캐시를 만든 경우

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

그런 다음, 이 명령을 사용하여 설치를 실행합니다.

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

> [!NOTE]
> 서명이 올바르지 않다는 오류가 발생하면 업데이트된 인증서를 설치해야 합니다. 오프라인 캐시에서 인증서 폴더를 엽니다. 각 인증서 파일을 두 번 클릭하고 인증서 관리자 마법사를 클릭합니다. 암호를 묻는 메시지가 표시되면 비워 두세요.

### <a name="list-of-language-locales"></a>언어 로캘 목록

| **언어 로캘** | **언어** |
| ----------------------- | --------------- |
| cs-CZ | 체코어 |
| de-DE | 독일어 |
| ko-KR | 영어 |
| es-ES | 스페인어 |
| fr-FR | 프랑스어 |
| it-IT | 이탈리아어 |
| ja-JP | 일본어 |
| ko-KR | 한국어 |
| pl-PL | 폴란드어 |
| pt-BR | 포르투갈어 - 브라질 |
| ru-RU | 러시아어 |
| tr-TR | 터키어 |
| zh-CN | 중국어 - 간체 |
| zh-TW | 중국어 - 번체 |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>참고 항목

- [Visual Studio 2017의 네트워크 설치 만들기](../install/create-a-network-installation-of-visual-studio.md)
- [Visual Studio 오프라인 설치에 필요한 인증서 설치](../install/install-certificates-for-visual-studio-offline.md)
- [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
- [Visual Studio 2017 워크로드 및 구성 요소 ID](workload-and-component-ids.md)
