---
title: Visual Studio 배포에 대한 업데이트 제어
description: 네트워크에서 설치할 때 Visual Studio에서 업데이트를 찾는 위치를 변경하는 방법을 알아봅니다.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24a8f49c036ed28693d92b162a417114f2c93e89
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704839"
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>네트워크 기반 Visual Studio 배포에 대한 업데이트 제어

엔터프라이즈 관리자는 때때로 레이아웃을 만들고 최종 사용자에게 배포하기 위해 네트워크 파일 공유에서 레이아웃을 호스트합니다.

## <a name="controlling-where-visual-studio-looks-for-updates"></a>Visual Studio가 업데이트를 검색하는 위치 제어

설치가 네트워크 공유에서 배포된 경우에도 기본적으로 Visual Studio에서는 온라인으로 업데이트를 계속 검색합니다. 업데이트가 사용 가능한 경우 사용자는 업데이트를 설치할 수 있습니다. 오프라인 레이아웃에 없는 업데이트된 콘텐츠는 웹에서 다운로드됩니다.

Visual Studio가 업데이트를 검색하는 위치를 직접 제어하려면 Visual Studio가 검색하는 위치를 수정할 수 있습니다. 사용자가 업데이트되는 버전도 제어할 수 있습니다. 이렇게 하려면 다음이 단계를 수행하세요.

 1. 오프라인 레이아웃을 만듭니다.
    ```cmd
    vs_enterprise.exe --layout C:\vs2017offline --lang en-US
    ```
 2. 레이아웃을 호스트할 파일 공유로 복사합니다.
    ```cmd
    xcopy /e C:\vs2017offline \\server\share\VS2017
    ```
 3. 레이아웃에서 response.json 파일을 수정하고 `channelUri` 값을 변경하여 관리자가 제어하는 channelManifest.json 복사본을 가리킵니다.

  다음 예제와 같이 값에서 백슬래시를 이스케이프해야 합니다.

  ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
  ```

 이제 최종 사용자는 이 공유에서 설치 프로그램을 실행하여 Visual Studio를 설치할 수 있습니다.
    ```cmd
    \\server\share\VS2017\vs_enterprise.exe
    ```

엔터프라이즈 관리자가 사용자가 최신 버전의 Visual Studio로 업데이트할 시점을 결정할 경우 다음과 같이 [레이아웃 위치를 업데이트](update-a-network-installation-of-visual-studio.md)하여 업데이트된 파일을 통합할 수 있습니다.

 1. 다음 명령과 비슷한 명령을 사용합니다.
    ```cmd
    vs_enterprise.exe --layout \\server\share\VS2017 --lang en-US
    ```
 2. 업데이트된 레이아웃의 response.json 파일에 사용자 지정, 특히 다음과 같은 channelUri 수정이 포함되어 있는지 확인합니다.
    ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
    ```
 이 레이아웃의 기존 Visual Studio 설치는 `\\server\share\VS2017\ChannelManifest.json`에서 업데이트를 검색합니다. 이 channelManifest.json이 사용자가 설치한 것보다 최신 버전인 경우 Visual Studio에서는 사용자에게 사용 가능한 업데이트가 있음을 알립니다.

 새로운 설치를 통해 레이아웃에서 직접 Visual Studio의 업데이트된 버전이 자동으로 설치됩니다.

## <a name="controlling-notifications-in-the-visual-studio-ide"></a>Visual Studio IDE에서 알림 제어

앞의 설명대로 Visual Studio에서는 설치가 시작된 위치(예: 네트워크 공유 또는 인터넷)를 확인하여 사용 가능한 업데이트가 있는지 확인합니다. 사용 가능한 업데이트가 있을 경우 Visual Studio에서는 창의 오른쪽 위에 알림 플래그를 표시하여 사용자에게 알립니다.

 ![업데이트 알림 플래그](media/notification-flag.png)

최종 사용자에게 업데이트를 알리지 않으려는 경우 알림을 사용하지 않도록 설정할 수 있습니다. (예를 들어, 하려는 중앙 소프트웨어 배포 메커니즘을 통해 업데이트를 제공하는 경우 알림을 사용하지 않도록 설정할 수 있습니다.)

Visual Studio 2017에서는 [레지스트리 항목을 개인 레지스트리에 저장](tools-for-managing-visual-studio-instances.md#editing-the-registry-for-a-visual-studio-instance)하므로 레지스트리를 일반적인 방법으로 직접 편집할 수 없습니다. 하지만 Visual Studio에는 Visual Studio 설정을 변경하는 데 사용할 수 있는 `vsregedit.exe` 유틸리티가 포함되어 있습니다. 다음 명령으로 알림을 끌 수 있습니다.

```cmd
vsregedit.exe set "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" HKCU ExtensionManager AutomaticallyCheckForUpdates2Override dword 0
```

편집할 설치된 인스턴스와 일치하도록 디렉터리를 바꾸어야 합니다.

> [!TIP]
> [vswhere.exe](tools-for-managing-visual-studio-instances.md#detecting-existing-visual-studio-instances)를 사용하여 클라이언트 워크스테이션에서 Visual Studio의 특정 인스턴스를 찾습니다.

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 인스턴스 관리 도구](tools-for-managing-visual-studio-instances.md)
