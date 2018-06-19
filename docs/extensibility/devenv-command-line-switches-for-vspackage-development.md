---
title: VSPackage 개발에 대 한 Devenv 명령줄 스위치 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- /setup command line switch
- /resetskippkgs command line switch
- /noVSIP command line switch
- /rootsuffix command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b6ad615048255452fc5642f8680b586d69587db5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134385"
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>VSPackage 개발에 대 한 Devenv 명령줄 스위치
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] devenv.exe를 Visual Studio 통합된 개발 환경 (IDE)를 시작 하는 파일을 실행할 때 명령줄에서 작업을 자동화 하는 개발자가 있습니다.  
  
 작업은 다음과 같습니다.  
  
-   IDE 외부에서 미리 정의 된 구성에서 응용 프로그램을 배포 합니다.  
  
-   자동으로 사전 설정을 사용 하 여 프로젝트의 빌드 설정을 빌드하거나 디버그 구성 합니다.  
  
-   IDE 외부 모두에서 특정 구성에서 IDE를 로드 합니다. 또한 시작 시 IDE를 사용자 지정할 수 있습니다.  
  
## <a name="guidelines-for-switches"></a>스위치에 대 한 지침  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설명서는 사용자 수준 devenv 명령줄 스위치에 설명 합니다. 자세한 내용은 참조 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)합니다. 또한 Devenv VSPackage 개발, 배포 및 디버깅에 유용한 추가 명령줄 스위치를 지원 합니다.  
  
|명령줄 스위치|설명|  
|--------------------------|-----------------|  
|/safemode|시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 안전 모드에서 기본 IDE 및 서비스를 로드 합니다. /Safemode 스위치에서 로드 될 때 모든 공급 업체 Vspackage 방지 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 시작 되 면 안정적으로 실행 되도록 합니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
|/resetskippkgs|문제가 있는 Vspackage, 로드를 방지 하려면 사용자가 추가 된 로드 옵션을 건너뛸 모든 지웁니다 다음 시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. SkipLoading 태그의 존재는 VSPackage 로드를 하는 사용 하지 않습니다. 태그를 지우면 VSPackage 로드 하는 다시 설정 합니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
|/rootsuffix|시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대체 위치를 사용 하 여 합니다. 다음 명령을 실행 하 여 만든 바로 가기가 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 설치 관리자:<br /><br /> devenv /RootSuffix exp<br /><br /> 이 경우 exp 10.0 보다는 10.0Exp 예를 들어 특정 접미사를 사용 하 여 위치를 식별합니다. 실험적 인스턴스를 사용 하는 VSPackage의 인스턴스에서 개별적으로 디버깅할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드를 작성 하는 사용 하는 합니다.<br /><br /> 이 스위치는 VSRegEx.exe를 사용 하 여 만든 위치를 식별 하는 모든 문자열을 사용할 수 있습니다. 자세한 내용은 참조 [의 실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.|  
|/splash|표시는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 평소와 같이 시작 화면 및 주 IDE를 표시 하기 전에 메시지 상자를 표시 합니다. 메시지 상자 예를 들어 VSPackage 제품 아이콘에 대 한 확인 하려면 시작 화면을 학습할 수 있습니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [명령줄 스위치를 추가합니다.](../extensibility/adding-command-line-switches.md)   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)