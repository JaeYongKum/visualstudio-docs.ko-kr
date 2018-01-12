---
title: "게시 페이지, 프로젝트 디자이너 (Visual Studio에서 Office 개발) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectProperties.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio]
- publishing, Office solutions
- Property Pages dialog box, Publish [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d9cc3fa102c0552893c6f7859a256b7df26e3af5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="publish-page-project-designer-office-development-in-visual-studio"></a>게시 페이지, 프로젝트 디자이너(Visual Studio에서는 Office 개발)
  **프로젝트 디자이너** 의 **게시** 페이지를 통해 배포를 위한 속성을 구성합니다.  
  
 이 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 *Projectname* **속성**을 선택합니다. **게시** 페이지가 표시되지 않으면 **게시** 탭을 선택합니다.  
  
> [!NOTE]  
>  게시 위치를 **게시 마법사**에서 설정할 수도 있습니다. 자세한 내용은 [방법: ClickOnce를 사용하여 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)을 참조하세요.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **폴더 위치 게시(웹 사이트, ftp 서버 또는 파일 경로)**  
 필수.  
  
 게시 폴더 위치는 Visual Studio가 빌드에서 매니페스트, 어셈블리 및 기타 파일과 같은 솔루션 파일을 복사하는 디렉터리입니다. 이 디렉터리에 쓰기 권한이 있어야 합니다.  
  
 옵션에는 로컬 컴퓨터, UNC 파일 공유 또는 HTTP/HTTPS 웹 사이트가 포함됩니다. 경로 로컬 일 수 있습니다 (*c:\foldername\publishfolder*), 상대 (*게시\\*), 또는 정규화 된 위치 (*\\\servername\foldername* 또는 http://*servername/foldername*).  
  
 기본적으로 게시 위치는 IIS를 설치한 경우 *http://localhost/projectname/* 이고, IIS를 설치하지 않은 경우 publish\ 디렉터리입니다.  
  
 **설치 폴더 URL**  
 선택 사항입니다.  
  
 설치 폴더 URL은 최종 사용자가 사용자 지정을 설치하는 디렉터리입니다. 또한 솔루션에서 업데이트를 확인하는 데 사용하는 경로이기도 합니다. 경로는 게시 폴더 위치와 동일할 수 있지만 이것이 요구 사항은 아닙니다.  
  
 옵션에는 로컬 컴퓨터, UNC 파일 공유 또는 HTTP/HTTPS 웹 사이트가 포함됩니다. 경로 로컬 일 수 있습니다 (*c:\foldername\publishfolder*), 상대 (*게시\\*), 또는 정규화 된 위치 (*\\\servername\foldername* 또는 http://*servername/foldername*). 모든 HTTP/HTTPS 위치는 US ASCII 문자로 만들어야 합니다. 유니코드 문자는 지원되지 않습니다.  
  
 설치 경로가 설정된 경우 사용자가 사용자 지정을 설치하려면 해당 위치에 사용자 지정 파일이 있어야 합니다. 최종 배포 위치를 알고 있는 경우에만 위치를 설정해야 합니다.  
  
 설치 파일이 CD 옵션 사용과 같이 문서 또는 설치 프로그램의 상대적인 위치에 있는 경우 이 상자를 비워 둡니다.  
  
 이 값은 관리자가 나중에 할당할 수 있습니다. 자세한 내용은 [Office 솔루션의 설치 경로 변경 방법](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)을 참조하세요.  
  
 **필수 구성 요소**  
 필수 조건은 설치 프로그램에 포함되거나 설치하는 동안 필요에 따라 다운로드할 수 있습니다.  
  
-   **구성 요소 공급업체의 웹 사이트에서 필수 조건 다운로드**: 이 옵션을 사용하여 Microsoft에서 이러한 필수 조건을 다운로드합니다.  
  
-   **내 응용 프로그램과 동일한 위치에서 필수 조건 다운로드**: 이 옵션을 사용하여 설치 관리자에서 필수 조건을 패키지에 포함시킵니다. 설치 프로그램에 필수 조건 파일을 포함하면 솔루션 크기가 늘어납니다.  
  
-   **다음 위치에서 필수 조건 다운로드**: 이 옵션을 사용하여 웹 페이지 또는 네트워크 공유의 다른 설치 프로그램처럼 필수 조건을 최종 사용자가 개별적으로 사용할 수 있게 합니다.  
  
 **Updates**  
 업데이트 간격은 솔루션이 업데이트를 확인하는 빈도를 결정합니다. 기본값은 7일마다 확인하는 것입니다.  
  
 문서 수준 사용자 지정 또는 VSTO 추가 기능이 로드될 때마다 업데이트를 확인하면 지속적으로 업데이트는 되지만 시작 성능에 영향을 줍니다.  
  
 CD 또는 이동식 드라이브를 사용하여 배포하는 경우 이 옵션을 **업데이트 확인 안 함**으로 설정합니다.  
  
 **옵션(설명)**  
 다음 속성에 대한 게시 옵션을 설정할 수 있습니다.  
  
-   게시 언어: Office 솔루션의 로캘  
  
-   게시자 이름: **프로그램 추가/제거** 또는 **프로그램 및 기능**에 표시되는 회사 또는 개발자 이름  
  
-   제품 이름: **프로그램 추가/제거** 또는 **프로그램 및 기능**에 표시되는 Office 솔루션의 이름  
  
-   지원 URL: 최종 사용자가 Office 솔루션에 대한 기술 지원에 문의하는 위치  
  
 **옵션(Office 설정)**  
 다음 속성에 대한 게시 옵션을 설정할 수 있습니다.  
  
-   솔루션 이름: Office 응용 프로그램에 표시되는 Office 솔루션의 이름  
  
-   설명: Office 응용 프로그램에 표시되는 Office 솔루션에 대한 설명  
  
-   VSTO 추가 기능 로드 동작  
  
    -   시작 시 로드: Office 응용 프로그램이 시작될 때 VSTO 추가 기능이 로드되도록 지정합니다.  
  
    -   요청 시 로드: 사용자가 VSTO 추가 기능의 기능을 사용하는 UI 요소를 클릭할 때처럼 VSTO 추가 기능이 응용 프로그램에서 필요로 할 때 로드되도록 지정합니다.  
  
 **게시 언어**  
 이 옵션은 Microsoft 소프트웨어 사용 조건의 언어를 설정하고 필수 조건 목록에 언어 팩을 포함합니다. 사용자 지정의 언어에는 영향을 주지 않습니다. 설치 프로그램의 언어는 Visual Studio의 설치된 언어에 의해 결정됩니다.  
  
 **게시 언어**를 변경하는 방법에 대한 자세한 내용은 [How to: Change the Publish Language for a ClickOnce Application](/visualstudio/deployment/how-to-change-the-publish-language-for-a-clickonce-application)을 참조하세요.  
  
 **게시 버전**  
 사용자 지정에 버전 번호를 설정합니다. 버전 번호가 변경되면 응용 프로그램이 업데이트로 게시됩니다. 이전에 게시된 버전을 덮어쓰지 않도록 빌드 프로세스 동안 각 버전에 대해 새 폴더가 만들어집니다. 게시 버전의 각 부분(**주**, **부**, **빌드**, **수정**)에는 최대 5개의 숫자가 포함될 수 있습니다.  
  
 **릴리스할 때마다 자동으로 수정 번호 증가**  
 선택 사항입니다. 선택된 경우(기본값), 버전 번호의 **수정** 부분이 사용자 지정을 게시할 때마다 1씩 증가합니다. 그러면 사용자 지정이 업데이트로 게시됩니다.  
  
 **지금 게시**  
 현재 설정을 사용하여 응용 프로그램을 게시합니다. **게시 마법사** 의 **마침**단추와 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office 솔루션 배포 필수 조건](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)  
  
  