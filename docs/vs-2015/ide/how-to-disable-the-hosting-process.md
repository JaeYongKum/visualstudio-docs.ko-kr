---
title: '방법: 호스팅 프로세스 비활성화 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2a3c2eee43d333ee7b58907a8471f4be9815bd47
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542485"
---
# <a name="how-to-disable-the-hosting-process"></a>How to: Disable the Hosting Process
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: Disable the Hosting Process](https://docs.microsoft.com/visualstudio/ide/how-to-disable-the-hosting-process)합니다.  
  
호스팅 프로세스를 사용하면 특정 API에 대한 호출에 영향이 있을 수 있습니다. 이 경우 올바른 결과를 반환하기 위해 호스팅 프로세스를 사용하지 않도록 설정해야 합니다.  
  
### <a name="to-disable-the-hosting-process"></a>호스팅 프로세스를 사용하지 않도록 설정하려면  
  
1.  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 실행 가능 프로젝트를 엽니다. 실행 파일을 생성하지 않는 프로젝트(예: 클래스 라이브러리 또는 서비스 프로젝트)에는 이 옵션이 없습니다.  
  
2.  **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
3.  **디버그** 탭을 클릭합니다.  
  
4.  **Visual Studio 호스팅 프로세스 사용** 확인란을 선택 취소합니다.  
  
 호스팅 프로세스가 사용하지 않도록 설정되면 여러 디버깅 기능을 사용할 수 없으며 성능 저하가 발생합니다. 자세한 내용은 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)를 참조하세요.  
  
 일반적으로 호스팅 프로세스는 사용하지 않습니다.  
  
-   [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 응용 프로그램 디버깅을 시작하는 데 필요한 시간이 증가합니다.  
  
-   디자인 타임 식 계산을 사용할 수 없습니다.  
  
-   부분 신뢰 디버깅을 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)   
 [호스팅 프로세스(vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [응용 프로그램 개발 중 빌드](http://msdn.microsoft.com/en-us/c9497d62-3b7b-4449-88e8-cf27acc9efe6)



