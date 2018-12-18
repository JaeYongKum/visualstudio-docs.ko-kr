---
title: -Upgrade(devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba94a599c119d537efb90b29c1c2ec0084ace447
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948337"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
솔루션 파일 및 모든 프로젝트 파일이나 지정한 프로젝트 파일을 이러한 파일의 현재 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 형식으로 업데이트합니다.

## <a name="syntax"></a>구문

```cmd
devenv SolutionFile | ProjectFile /upgrade
```

## <a name="arguments"></a>인수
 `SolutionFile`

 전체 솔루션 및 해당 프로젝트를 업그레이드할 경우 필요합니다. 솔루션 파일의 경로 및 이름입니다. 솔루션 파일의 이름만 입력하거나 솔루션 파일의 전체 경로와 이름을 입력할 수 있습니다. 이름이 지정된 폴더나 파일이 아직 없으면 새로 만들어집니다.

 `ProjectFile`

 단일 프로젝트를 업그레이드할 경우 필요합니다. 솔루션 내에 있는 프로젝트 파일의 경로와 이름입니다. 프로젝트 파일의 이름만 입력하거나 프로젝트 파일의 전체 경로와 이름을 입력할 수 있습니다. 이름이 지정된 폴더나 파일이 아직 없으면 새로 만들어집니다.

## <a name="remarks"></a>설명
 백업은 자동으로 만들어지고 현재 디렉터리에 생성된 Backup 디렉터리로 복사됩니다.

 소스 제어 솔루션 또는 프로젝트는 업그레이드하기 전에 체크 아웃해야 합니다.

 `/upgrade` 스위치를 사용해도 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 시작되지 않습니다. 솔루션 또는 프로젝트의 개발 언어에 대한 업그레이드 보고서에서 업그레이드 결과를 확인할 수 없습니다. 오류 또는 사용 정보가 반환되지 않습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../../porting/port-migrate-and-upgrade-visual-studio-projects.md)를 참조하세요.

## <a name="example"></a>예
 이 예제에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 솔루션에 대한 기본 폴더에서 “MyProject.sln”이라는 솔루션 파일을 업그레이드합니다.

```cmd
devenv "MyProject.sln" /upgrade
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)