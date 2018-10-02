---
title: 고급 보안 설정 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
- vs.err.debug_in_zone_no_hostproc:11310
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 72b8bb7f6301672e89c54c9fa73a72bad8148999
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549585"
---
# <a name="advanced-security-settings-dialog-box"></a>고급 보안 설정 대화 상자
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [고급 보안 설정 대화 상자](https://docs.microsoft.com/visualstudio/ide/reference/advanced-security-settings-dialog-box)합니다.  
  
  
이 대화 상자를 사용하면 영역 디버깅과 관련된 보안 설정을 지정할 수 있습니다.  
  
 이 대화 상자에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 **프로젝트** 메뉴에서 **속성**을 클릭합니다. **프로젝트 디자이너**가 나타나면 **보안** 탭을 클릭합니다. **보안** 페이지에서 **ClickOnce 보안 설정 사용**을 선택하고 **부분 신뢰 응용 프로그램**을 클릭한 후 **고급**을 클릭합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **선택한 권한 집합으로 이 응용 프로그램 디버깅**  
 이 확인란을 선택하면 **보안** 페이지에서 선택한 권한 집합이 디버깅 중에 사용됩니다. 기본적으로 이 옵션이 선택됩니다.  
  
 보안 영역에서 디버깅을 작동시키려면 이 옵션을 사용하도록 설정해야 합니다. 또한 **Visual Studio 호스팅 프로세스 사용** 옵션(**프로젝트 디자이너**의 **디버그** 페이지에서 사용 가능)을 사용하도록 설정해야 합니다.  
  
 WPF 웹 브라우저 응용 프로그램 프로젝트에서는 **선택한 권한 집합으로 이 응용 프로그램 디버깅** 옵션을 선택하고 사용하지 않도록 설정합니다.  
  
 **원본 사이트에 응용 프로그램 액세스 허용**  
 이 확인란을 선택하면 응용 프로그램은 게시된 웹 사이트 또는 서버 공유에 액세스할 수 있습니다. 기본적으로 이 옵션이 선택됩니다.  
  
 **다음 URL에서 다운로드한 것처럼 이 응용 프로그램을 디버깅**  
 응용 프로그램이 **게시** 페이지에 지정한 **설치 URL**에 해당하는 웹 사이트 또는 서버 공유에 액세스하도록 허용하려면 여기에 URL을 입력합니다. 이 옵션은 **원본 사이트에 응용 프로그램 액세스 허용**을 선택한 경우에만 사용 가능합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 디자이너, 보안 페이지](../../ide/reference/security-page-project-designer.md)



