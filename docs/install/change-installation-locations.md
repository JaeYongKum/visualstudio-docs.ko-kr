---
title: Visual Studio 2017에서 설치 위치 선택
description: 다운로드 캐시, 공유 구성 요소, 일부 SDK 및 도구의 위치를 다른 드라이브로 변경하여 시스템 드라이브의 설치 공간을 줄이는 방법을 알아봅니다.
ms.date: 11/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- select an installation location for Visual Studio files
- move installation files to different drives
- use the D drive
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed3b54674c24e3becf62e7568be127344104de0f
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295035"
---
# <a name="select-the-installation-locations-in-visual-studio-2017"></a>Visual Studio 2017에서 설치 위치 선택

**15.7의 새로운 기능**: 해당 파일의 일부의 위치를 변경하여 시스템 드라이브에서 Visual Studio의 설치 공간을 줄일 수 있습니다. 특히 다운로드 캐시, 공유 구성 요소, SDK 및 도구 파일에 대해 다른 위치를 사용할 수 있습니다.

   > [!NOTE]
   > 일부 도구와 SDK를 설치할 수 있는 위치에 다른 규칙이 적용되는 도구와 SDK가 있습니다. 이러한 도구 및 SDK는 다른 위치를 선택했다 하더라도 시스템 드라이브에 설치됩니다.

시작할 준비가 되셨나요? 방법은 다음과 같습니다.

1. Visual Studio를 설치할 때 **설치 위치** 탭을 선택합니다.

   ![Visual Studio 2017 - 설치 위치 선택](media/vs-installation-locations.png "설치 위치를 선택합니다.")

1. **Visual Studio IDE** 섹션에서 기본값을 적용합니다. Visual Studio에서는 핵심 제품을 설치하고 이 Visual Studio 버전에 특정한 파일을 포함합니다.

   ![설치 위치 탭의 Visual Studio IDE 섹션](media/vs-installation-locations-ide.png "설치 위치 탭의 Visual Studio IDE 섹션에 대한 기본값을 적용합니다.")

   > [!TIP]
   > 시스템 드라이브가 SSD(solid-state drive)인 경우 기본 위치를 시스템 드라이브에 적용하는 것이 좋습니다. 이유는? Visual Studio를 사용하여 개발하는 경우 디스크 I/O 작업을 증가시키는 많은 파일을 읽고 쓰고합니다. 로드를 처리하기 위해 가장 빠른 드라이브를 선택하는 것이 좋습니다.

1. **다운로드 캐시** 섹션에서 다운로드 캐시를 유지할지 여부를 결정한 다음, 해당 파일을 저장하려는 위치를 결정합니다.

     ![설치 위치 탭의 캐시 섹션 다운로드](media/vs-installation-locations-cache.png "설치 후 다운로드 캐시를 유지할지 여부를 선택한 다음, 파일을 저장하려는 드라이브를 지정합니다.")

    1. **설치 후 다운로드 캐시 유지**를 선택하거나 선택을 취소합니다.

       다운로드 캐시를 유지하지 않도록 설정하면 위치를 일시적으로만 사용합니다. 이 작업은 이전 설치에서 파일에 영향을 주지도 파일을 삭제하지도 않습니다.

    1. 다운로드 캐시에서 설치 파일과 매니페스트를 저장하려는 드라이브를 지정합니다.

        예를 들어, "C++을 통한 데스크톱 개발"을 선택할 경우 일시적으로 필요한 크기는 시스템 드라이브에서 1.58GB이며 설치가 완료된 즉시 비워집니다.

       > [!IMPORTANT]
       > 이 위치는 처음 설치에서 설정되며 이후 설치 관리자 UI에서는 변경할 수 없습니다. 대신, [명령줄 매개 변수를 사용하여](use-command-line-parameters-to-install-visual-studio.md) 다운로드 캐시를 이동해야 합니다.

1. **공유 구성 요소, 도구 및 SDK** 섹션에서 함께 설치한 Visual Studio에서 공유하는 파일을 저장하려는 드라이브를 지정합니다. SDK 및 도구는 이 디렉터리에도 저장됩니다.

   ![설치 위치 탭의 공유 구성 요소, 도구 및 SDK 섹션](media/vs-installation-locations-shared.png "공유 구성 요소, 도구 및 SDK를 저장하려는 위치를 지정합니다.")

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 2017 업데이트](update-visual-studio.md)
* [Visual Studio 2017 수정](update-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
