---
title: '방법: SharePoint 배포 명령 설정 | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 98aedc0c7fa557a45b43ab8344a49587b8febec1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920367"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>방법: SharePoint 배포 명령 설정
  배포 전 및 배포 후 명령을 설정 하 여 배포 프로세스를 사용자 지정할 수 있습니다. 이러한 명령은 Visual Studio에서 SharePoint 솔루션을 디버깅할 때 다른 배포 작업 전후에 실행 됩니다.  
  
### <a name="to-add-a-pre-deployment-command"></a>배포 전 명령을 추가 하려면  
  
1.  메뉴 모음에서 선택 **프로젝트** > **\<*ProjectName*> 속성**합니다.  
  
2.  선택 된 **SharePoint** 탭 합니다.  
  
3.  에 **배포 전 명령줄** 텍스트 상자에이 단계를 사용자 지정할 MS-DOS 또는 MSBuild 명령을 입력 합니다.  
  
     예를 들어 입력 배포가 완료 되기 전에 디렉터리 콘텐츠를 나타내려면 **dir**합니다.  
  
### <a name="to-add-a-post-deployment-command"></a>배포 후 명령을 추가 하려면  
  
1.  메뉴 모음에서 선택 **프로젝트** > **\<*ProjectName*> 속성**합니다.  
  
2.  선택 된 **SharePoint** 탭 합니다.  
  
3.  에 **배포 후 명령줄** 텍스트 상자에이 단계를 사용자 지정할 MS-DOS 또는 MSBuild 명령을 입력 합니다.  
  
     예를 들어, 배포가 완료 된 후에 디렉터리 콘텐츠를 나열 하려면 입력 **dir**합니다. 빌드 디렉터리에서 어셈블리를 복사 하는 MSBuild 변수를 사용 하려면 입력 **$ (targetpath) c:\DeploymentDirectory 복사**합니다.  
  
## <a name="see-also"></a>참고 항목
 [패키지 및 SharePoint 솔루션 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
