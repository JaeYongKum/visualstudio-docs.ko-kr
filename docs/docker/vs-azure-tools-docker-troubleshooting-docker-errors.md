---
title: Windows에서 Docker 클라이언트 오류 해결 | Microsoft Docs
description: Visual Studio 2017을 사용하여 웹앱을 만들고 Docker에 배포하는 경우 발생하는 문제를 해결합니다.
services: azure-container-service
author: devinb
manager: jillfra
ms.custom: seodec18
ms.assetid: 346f70b9-7b52-4688-a8e8-8f53869618d3
ms.service: multiple
ms.devlang: dotnet
ms.topic: conceptual
ms.workload: multiple
ms.date: 10/13/2017
ms.author: devinb
ms.openlocfilehash: a96f9792fa4922a626d4740625d361751242e39b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55140774"
---
# <a name="troubleshoot-visual-studio-2017-development-with-docker"></a>Docker를 사용한 Visual Studio 2017 개발 문제 해결

Visual Studio Tools for Docker로 작업할 때 애플리케이션 빌드 또는 디버깅 중에 문제가 발생할 수도 있습니다. 다음은 몇 가지 일반적인 문제 해결 단계입니다.

## <a name="volume-sharing-is-not-enabled-enable-volume-sharing-in-the-docker-ce-for-windows-settings--linux-containers-only"></a>볼륨 공유 사용 안 함. Windows용 Docker CE 설정(Linux 컨테이너에만 해당)에 볼륨 공유 사용

이 문제를 해결하려면:

1. 알림 영역에서 **Windows용 Docker**를 마우스 오른쪽 단추로 클릭한 다음 **설정**을 선택합니다.
1. **공유 드라이브**를 선택하고 프로젝트가 있는 드라이브와 함께 시스템 드라이브를 공유합니다.

> [!NOTE]
> 파일이 공유됨으로 나타나면, 볼륨 공유를 다시 사용하도록 설정하기 위해 대화 상자의 맨 아래에 있는 "자격 증명 재설정..." 링크를 여전히 클릭해야 합니다. 자격 증명을 다시 설정한 후 계속 진행하려면 Visual Studio를 다시 시작해야 할 수 있습니다.

![공유 드라이브](media/vs-azure-tools-docker-troubleshooting-docker-errors/shareddrives.png)

> [!TIP]
> Visual Studio 2017 버전 15.6 이상은 **공유 드라이브**가 구성되지 않은 경우 메시지를 표시합니다.

### <a name="container-type"></a>컨테이너 유형

프로젝트에 Docker 지원을 추가할 때 Windows 또는 Linux 컨테이너를 선택할 수 있습니다. Docker 호스트는 동일한 컨테이너 형식을 실행 중이어야 합니다. 실행 중인 Docker 인스턴스에서 컨테이너 형식을 변경하려면 시스템 트레이의 Docker 아이콘을 마우스 오른쪽 단추로 클릭하고 **Windows 컨테이너로 전환** 또는 **Linux 컨테이너로 전환**을 선택합니다.

## <a name="unable-to-start-debugging"></a>디버깅을 시작할 수 없음

한 가지 이유로 사용자 프로필 폴더에 부실 디버깅 구성 요소가 있는 것과 관련 있을 수 있습니다. 다음 디버그 세션에 최신 디버깅 구성 요소가 다운로드되도록 하려면 다음 명령을 실행하여 이러한 폴더를 제거합니다.

- del %userprofile%\vsdbg
- del %userprofile%\onecoremsvsmon

## <a name="errors-specific-to-networking-when-debugging-your-application"></a>애플리케이션을 디버깅할 때 네트워킹에 국한되는 오류

호스트 컴퓨터에서 네트워크 관련 구성 요소를 새로 고침할 [정리 컨테이너 호스트 네트워킹](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-server-container-tools/CleanupContainerHostNetworking)에서 다운로드할 수 있는 스크립트를 실행 시도합니다.

## <a name="mounts-denied"></a>탑재 거부됨

macOS용 Docker를 사용하는 경우 /usr/local/share/dotnet/sdk/NuGetFallbackFolder 폴더를 참조할 때 오류가 발생할 수 있습니다. Docker에서 파일 공유 탭에 폴더 추가

## <a name="microsoftdockertools-github-repo"></a>Microsoft/DockerTools GitHub 리포지토리

다른 문제가 발생하면, [Microsoft/DockerTools](https://github.com/microsoft/dockertools/issues) 문제를 참조하세요.