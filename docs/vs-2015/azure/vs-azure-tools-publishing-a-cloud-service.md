---
title: Azure Tools를 사용 하 여 클라우드 서비스 게시 | Microsoft Docs
description: Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트를 게시 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 1a07b6e4-3678-4cbf-b37e-4520b402a3d9
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: cf29e1cdde71d2e8ef7caa9bc91bc31c30c7bc41
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002858"
---
# <a name="publishing-a-cloud-service-using-visual-studio"></a>Visual Studio를 사용하여 클라우드 서비스 게시

Visual Studio 클라우드 서비스의 스테이징 슬롯과 프로덕션 환경에 대 한 지원 사용 하 여 Azure에 직접 응용 프로그램을 게시할 수 있습니다. 게시할 때 배포 환경 및 배포 패키지에 일시적으로 사용 되는 저장소 계정을 선택 합니다.

개발 하 고 Azure 응용 프로그램을 테스트 하 고, 웹 배포 하 여 웹 역할에 대 한 변경 내용을 증분 방식으로 게시 합니다. 배포 환경에 응용 프로그램을 게시 한 후 변경 사항을 웹 역할을 실행 하는 가상 컴퓨터에 직접 배포할 수 있습니다 웹 배포. 패키지 하 고 변경 내용을 테스트 하려면 웹 역할을 업데이트할 때마다 전체 Azure 응용 프로그램을 게시할 필요가 없습니다. 이 방법을 사용 하 여 사용할 수 있는 웹 역할 변경 사항을 때 배포 환경에 게시 된 응용 프로그램까지 기다리지 않고도 테스트를 위해 클라우드에 있습니다.

웹 배포를 사용 하 여 웹 역할을 업데이트 하 고 Azure 응용 프로그램을 게시 하는 데에 다음 절차를 사용 합니다.

- 게시 또는 Visual Studio에서 Azure 응용 프로그램 패키지
- 개발 및 테스팅 과정의 일환으로 웹 역할 업데이트

## <a name="publish-or-package-an-azure-application-from-visual-studio"></a>게시 또는 Visual Studio에서 Azure 응용 프로그램 패키지

Azure 응용 프로그램을 게시 하면 다음 작업 중 하나를 수행할 수 있습니다.

- 서비스 패키지 만들기: 응용 프로그램에서 배포 환경에 게시 하려면이 패키지 및 서비스 구성 파일을 사용할 수 있습니다 합니다 [Azure portal](https://portal.azure.com)합니다.

- Visual Studio에서 Azure 프로젝트 게시: 응용 프로그램을 직접 Azure에 게시 하려면 게시 마법사를 사용 합니다. 정보를 참조 하세요 [Azure 응용 프로그램 게시 마법사](vs-azure-tools-publish-azure-application-wizard.md)합니다.

### <a name="to-create-a-service-package-from-visual-studio"></a>Visual Studio에서 서비스 패키지를 만들려면

1. 응용 프로그램을 게시할 준비가 되었을 때 솔루션 탐색기를 열고, 사용자의 역할이 포함 된 Azure 프로젝트에 대 한 바로 가기 메뉴를 열고 및 게시를 선택 합니다.

1. 서비스 패키지만 만들려면 다음이 단계를 수행 합니다.

   a. Azure 프로젝트의 바로 가기 메뉴에서 선택 **패키지**합니다.

   b. 에 **Azure 응용 프로그램 패키지** 대화 상자에서 패키지를 만들려는 서비스 구성을 선택 하 고 빌드 구성을 선택 합니다.

   c. (선택 사항) 를 설정 하려면 원격 데스크톱에서 클라우드 서비스에 게시 한 후 선택 **모든 역할에 대 한 원격 데스크톱 사용**를 선택한 후 **설정** 원격 데스크톱 자격 증명을 구성 합니다. 자세한 내용은 [Visual Studio를 사용 하 여 Azure Cloud Services에서 역할에 대 한 원격 데스크톱 연결 사용](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)합니다.

      게시 후 클라우드 서비스를 디버그 하려는 경우 선택 하 여 원격 디버깅 설정 **모든 역할에 대해 원격 디버거 사용**합니다.

   d. 패키지를 만들려면 선택 합니다 **패키지** 링크 합니다.

      파일 탐색기에 새로 생성된 된 패키지의 파일 위치를 보여 줍니다. Azure portal에서 사용할 수 있도록이 위치를 복사할 수 있습니다.

   e. 이 패키지를 배포 환경에 게시를 사용 해야이 위치를 패키지 위치로 클라우드 서비스를 만들고 Azure portal 사용 하 여 환경에이 패키지를 배포 하는 경우.

1. (선택 사항) 활동 로그에서 품목에 대 한 바로 가기 메뉴에서 배포 프로세스를 취소 하려면 **취소 및 제거**합니다. 이 명령은 배포 프로세스를 중지 하 고 Azure에서 배포 환경이 삭제 합니다. 배포 후 환경을 제거 하려면 Azure portal을 사용 합니다.

1. (선택 사항) Visual Studio 배포 환경을 자동으로 표시 역할 인스턴스가 시작 된 후에 **Cloud Services** 서버 탐색기에서 노드. 여기에서 개별 역할 인스턴스의 상태를 볼 수 있습니다. 참조 [클라우드 탐색기를 사용 하 여 Azure 관리 리소스](vs-azure-tools-resources-managing-with-cloud-explorer.md)합니다. 다음 그림에서는 여전히 초기화 되는 동안 역할 인스턴스를 보여 줍니다.

    ![VST_DeployComputeNode](./media/vs-azure-tools-publishing-a-cloud-service/IC744134.png)

## <a name="update-a-web-role-as-part-of-the-development-and-testing-cycle"></a>개발 및 테스팅 과정의 일환으로 웹 역할 업데이트

앱의 백 엔드 인프라가 안정적 이지만 웹 역할은 더 자주 업데이트가 필요한 경우 웹 배포 하 여 프로젝트의 웹 역할만 업데이트 합니다. 웹 배포를 다시 작성 하 고 백 엔드 작업자 역할을 다시 배포 하지 않을 때 또는 여러 웹 역할이 있고 하나의 웹 역할만 업데이트 하려는 경우에 유용 합니다.

### <a name="requirements-for-using-web-deploy"></a>웹 배포 사용에 대 한 요구 사항

- **개발 및 테스트 목적 으로만**: 변경 내용이 가상 컴퓨터에 직접 웹 역할이 실행 되는 위치입니다. 이 가상 컴퓨터에 재활용 될 경우 변경 내용을 게시 하는 원래 패키지를 역할에 대 한 가상 컴퓨터를 다시 사용 되기 때문에 손실 됩니다. 웹 역할에 대 한 최신 변경 내용을 가져오려면 응용 프로그램을 다시 게시 합니다.

- **웹 역할만 업데이트할 수**: 작업자 역할을 업데이트할 수 없습니다. 또한 업데이트할 수 없습니다는 `RoleEntryPoint` 에서 `web role.cs`합니다.

- **웹 역할의 단일 인스턴스만 지원할 수**: 배포 환경의 웹 역할의 여러 인스턴스를 사용할 수 없습니다. 그러나 각각의 웹 역할 인스턴스 중 하나만 지원 됩니다.

- **원격 데스크톱 연결 사용**:이 요구 사항은 웹 배포가 사용자 이름 및 암호를 사용 하 여 인터넷 정보 서비스 (IIS)를 실행 하는 서버에 변경 내용을 배포 하는 가상 머신에 연결할 수 있습니다. 또한이 가상 컴퓨터에 IIS를 신뢰할 수 있는 인증서를 추가 하려면 가상 머신에 연결 해야 합니다. (이 인증서 하면 보안 웹 배포에서 사용 되는 IIS에 대 한 원격 연결입니다.)

다음 절차를 사용 하는 것으로 가정 합니다 **Azure 응용 프로그램 게시** 마법사.

### <a name="enable-web-deploy-when-you-publish-your-application"></a>응용 프로그램을 게시할 때 웹 배포 사용

1. 사용 하도록 설정 합니다 **모든 웹 역할에 대해 웹 배포 사용** 옵션을 먼저 원격 데스크톱 연결을 구성 해야 합니다. 선택 **원격 데스크톱 사용** 모든 역할에 대 한 다음 원격 연결에 사용 되는 자격 증명을 제공 합니다 **원격 데스크톱 구성** 상자가 표시 되 면 합니다. 참조 [Visual Studio를 사용 하 여 Azure Cloud Services에서 역할에 대 한 원격 데스크톱 연결 사용](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)합니다.

1. 을 사용 하려면 웹 배포 응용 프로그램에서 모든 웹 역할에 대 한 **모든 웹 역할에 대해 웹 배포 사용**합니다.

    노란색 경고 삼각형이 나타납니다. 웹 배포는 신뢰할 수 없는 자체 서명 된 인증서를 사용 하 여 기본적으로 중요 한 데이터를 업로드 하기 위한 권장 되지 않습니다. 중요 한 데이터에 대 한이 프로세스를 보호 해야 할 경우 웹 배포 연결에 사용할 SSL 인증서를 추가할 수 있습니다. 이 인증서는 신뢰할 수 있는 인증서를 해야 합니다. 자세한 내용은 [웹 배포를 안전 하 게](#make-web-deploy-secure)합니다.

1. 선택 **다음** 표시할 합니다 **요약** 화면을 선택한 후 **게시** 클라우드 서비스를 배포 합니다.

    클라우드 서비스 게시 됩니다. 만든 가상 컴퓨터에 다시 게시 하지 않고 웹 역할을 업데이트 하려면 웹 배포 사용 될 수 있도록 IIS에 대해 사용 하도록 설정 하는 원격 연결 합니다.

   > [!NOTE]
   > 웹 역할에 대해 구성 된 둘 이상의 인스턴스가 있을 경우 각 웹 역할이 하나의 인스턴스로 응용 프로그램을 게시 하기 위해 만든 패키지에만 제한 된다는 내용의 경고 메시지가 나타납니다. 선택 **확인** 를 계속 합니다. 요구 사항 섹션에서 설명 했 듯이 둘 이상의 웹 역할은 지원 되지만 역할당 하나의 인스턴스만 있을 수 있습니다.

### <a name="update-your-web-role-by-using-web-deploy"></a>웹 배포를 사용 하 여 웹 역할을 업데이트 합니다.

1. 웹 배포를 사용 하려면 코드를 변경한 게시 한 다음 솔루션에서이 프로젝트 노드를 마우스 오른쪽 단추로 클릭 및 가리킨 하려는 Visual Studio에서 웹 역할에 대 한 프로젝트 **게시**합니다. 합니다 **웹 게시** 대화 상자가 나타납니다.

1. (선택 사항) IIS에 대 한 원격 연결에 사용할 신뢰할 수 있는 SSL 인증서를 추가한 경우 선택을 취소할 수 있습니다 합니다 **신뢰할 수 없는 인증서 허용** 확인란 합니다. 보안 웹 배포를 구현 하기 위한 인증서를 추가 하는 방법에 대 한 자세한 내용은 **하려면 보안 웹 배포 구현** 이 문서의 뒷부분에 나오는.

1. 웹 배포를 사용 하려면 게시 메커니즘에는 사용자 이름 및 암호를 설정 하는 원격 데스크톱 연결에 대 한 패키지를 처음 게시할 때 필요 합니다.

   a. **사용자 이름**, 사용자 이름을 입력 합니다.

   b. **암호**, 암호를 입력 합니다.

   c. (선택 사항) 이 프로필에이 암호를 저장 하려는 경우 선택 **암호 저장**합니다.

1. 웹 역할에 변경 내용을 게시 하려면 선택할 **게시**합니다.

    상태 표시줄 표시 **게시 시작**합니다. 게시가 완료 되 면 **게시 성공** 나타납니다. 이제 변경 내용은 가상 컴퓨터에 웹 역할에 배포 되었습니다. 이제 변경 내용을 테스트 하 여 Azure 환경에서 Azure 응용 프로그램을 시작할 수 있습니다.

### <a name="make-web-deploy-secure"></a>웹 배포를 안전 하 게 보호

1. 웹 배포는 신뢰할 수 없는 자체 서명 된 인증서를 사용 하 여 기본적으로 중요 한 데이터를 업로드 하기 위한 권장 되지 않습니다. 중요 한 데이터에 대 한이 프로세스를 보호 해야 할 경우 웹 배포 연결에 사용할 SSL 인증서를 추가할 수 있습니다. 이 인증서는 인증 기관 (CA)에서 가져와야 하는 신뢰할 수 있는 인증서를 해야 합니다.

    웹 배포에 보안 구현 하려면 각 가상 머신에 대 한 각 웹 역할에 대 한 for web 사용 하려는 신뢰할 수 있는 인증서를 업로드 해야 Azure portal에 배포 합니다. 이 인증서는 인증서가 응용 프로그램을 게시할 때 웹 역할에 대해 생성 되는 가상 컴퓨터에 추가 했는지 확인 합니다.

1. IIS에서 원격 연결에 사용할에 신뢰할 수 있는 SSL 인증서를 추가 하려면 다음이 단계를 수행 합니다.

   a. 웹 역할을 실행 하는 가상 컴퓨터에 연결 하려면 웹 역할의 인스턴스를 선택 **클라우드 탐색기** 하거나 **서버 탐색기**를 선택한 후는 **원격 데스크톱을 사용 하 여 연결**  명령입니다. 가상 머신에 연결 하는 방법에 대 한 자세한 단계를 참조 하세요 [Visual Studio를 사용 하 여 Azure Cloud Services에서 역할에 대 한 원격 데스크톱 연결 사용](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)합니다. 브라우저는 다운로드 하 라는 메시지가 표시 됩니다는 `.rdp` 파일입니다.

   b. SSL 인증서를 추가 하려면 관리 서비스를 IIS 관리자에서 엽니다. IIS 관리자를 열어 SSL을 사용 합니다 **바인딩을** 링크를 **동작** 창입니다. 합니다 **사이트 바인딩 추가** 대화 상자가 나타납니다. 선택 **추가**를 선택한 후에 HTTPS를 **형식** 드롭 다운 목록. 에 **SSL 인증서** 목록에서 CA에서 서명 되 고 Azure portal에 업로드 된 SSL 인증서를 선택 합니다. 자세한 내용은 [관리 서비스에 대 한 연결 설정 구성](http://go.microsoft.com/fwlink/?LinkId=215824)합니다.

      > [!NOTE]
      > 신뢰할 수 있는 SSL 인증서를 추가 하는 경우 노란색 경고 삼각형이 더 이상 나타나지 않습니다 합니다 **게시 마법사**합니다.

## <a name="include-files-in-the-service-package"></a>서비스 패키지에 파일을 포함 합니다.

역할에 대해 만든 가상 컴퓨터에서 사용할 수 있도록 특정 파일을 서비스 패키지에 포함 해야 합니다. 추가 하려는 하는 예는 `.exe` 또는 `.msi` 서비스 패키지에 시작 스크립트에서 사용 되는 파일입니다. 또는 웹 역할 또는 작업자 역할 프로젝트에는 어셈블리를 추가 해야 합니다. 파일을 포함 하려면 이러한 Azure 응용 프로그램에 대 한 솔루션에 추가 되어야 합니다.

1. 어셈블리에 서비스 패키지를 추가 하려면 다음 단계를 사용 합니다.

   a. **솔루션 탐색기**, 참조 된 어셈블리가 누락 되는 프로젝트의 프로젝트 노드를 엽니다.
   b. 어셈블리에 프로젝트를 추가 하려면 바로 가기 메뉴를 열고 합니다 **참조** 폴더를 선택한 후 **참조 추가**합니다. 참조 추가 대화 상자가 나타납니다.
   c. 참조를 추가 하 고 선택 하려는 **확인**합니다. 아래의 목록에 참조가 추가 되는 **참조** 폴더입니다.
   d. 추가한 어셈블리에 대 한 바로 가기 메뉴를 열고 **속성**합니다. 합니다 **속성** 창이 나타납니다.

      서비스 패키지에서이 어셈블리에 포함 하는 **로컬 복사 목록** 선택 **True**합니다.
1. **솔루션 탐색기** 참조 어셈블리가 없는 프로젝트의 프로젝트 노드를 엽니다.

1. 어셈블리에 프로젝트를 추가 하려면 바로 가기 메뉴를 열고 합니다 **참조** 폴더를 선택한 후 **참조 추가**합니다. 합니다 **참조 추가** 대화 상자가 나타납니다.

1. 참조를 추가 하 고 선택 하려는 합니다 **확인** 단추입니다.

    아래의 목록에 참조가 추가 되는 **참조** 폴더입니다.

1. 추가한 어셈블리에 대 한 바로 가기 메뉴를 열고 **속성**합니다. 속성 창에 표시 됩니다.

1. 서비스 패키지에서이 어셈블리에 포함 하는 **로컬 복사** 목록에서 선택 **True**합니다.

1. 웹 역할 프로젝트에 추가 된 서비스 패키지에 파일을 포함 하려면 파일의 바로 가기 메뉴를 열고 선택한 후 **속성**합니다. **속성** 창에서 선택 **콘텐츠** 에서 **빌드 작업** 목록 상자입니다.

1. 작업자 역할 프로젝트에 추가 된 서비스 패키지에 파일을 포함 하려면 파일의 바로 가기 메뉴를 열고 선택한 후 **속성**합니다. **속성** 창 선택 **변경 된 내용만 복사** 에서 합니다 **출력 디렉터리에 복사** 목록 상자입니다.

## <a name="next-steps"></a>다음 단계

Visual Studio에서 Azure에 게시 하는 방법에 대 한 자세히 알아보려면, 참조 [Azure 응용 프로그램 게시 마법사](vs-azure-tools-publish-azure-application-wizard.md)합니다.
