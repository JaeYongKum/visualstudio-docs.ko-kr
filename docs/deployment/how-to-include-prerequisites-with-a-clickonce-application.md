---
title: '방법: ClickOnce 응용 프로그램에 필수 구성 요소를 포함 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54cdcdb89896662a6d4e474c7df2ee09cea4d8bf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31559061"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 포함
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 필요한 구성 요소 소프트웨어를 배포하기 전에 먼저 이러한 필수 구성 요소용 설치 관리자 패키지를 개발 컴퓨터로 다운로드해야 합니다. 응용 프로그램을 게시 하 고 선택 **내 응용 프로그램과 동일한 위치에서 필수 구성 요소 다운로드**, 설치 관리자 패키지에 없는 경우 오류가 발생 합니다는 **패키지** 폴더입니다.  
  
> [!NOTE]
>  .NET Framework에 대 한 설치 관리자 패키지를 추가 하려면 참조 [개발자를 위한.NET Framework 배포 가이드](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx)합니다.  
  
##  <a name="Package"></a> Package.xml을 사용 하 여 설치 관리자 패키지를 추가 하려면  
  
1.  파일 탐색기에서 열고는 **패키지** 폴더입니다.  
  
     기본적으로, 경로는 32비트 시스템의 경우 C:\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages이고 64비트 시스템의 경우 C:\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages입니다.  
  
2.  를 추가 하려는 필수 구성 요소에 대 한 폴더를 연 다음 설치 된 버전의 언어 폴더를 엽니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (예를 들어 **en** 영어에 대 한).  
  
3.  메모장에서 열고는 **Package.xml** 파일입니다.  
  
4.  찾을 **이름** 포함 된 요소 **http://go.microsoft.com/fwlink**, URL을 복사 합니다. 포함 된 **LinkID** 부분입니다.  
  
    > [!NOTE]
    >  없는 경우 **이름** 요소에 포함 되어 **http://go.microsoft.com/fwlink**열고는 **Product.xml** 필수 구성 요소에 대 한 루트 폴더에 파일을 찾습니다는 **fwlink** 문자열입니다.  
  
    > [!IMPORTANT]
    >  일부 필수 구성 요소에는 여러 개의 설치 관리자 패키지가 있습니다(예: 32비트 또는 64비트 시스템). 여러 개인 경우 **이름** 요소에 포함 된 **fwlink**, 각각의 나머지 단계를 반복 해야 합니다.  
  
5.  브라우저의 주소 표시줄에 URL을 붙여 넣은 다음를 실행 하거나 저장 하는 메시지가 때 선택 **저장**합니다.  
  
     이 단계에서는 설치 관리자 파일을 컴퓨터에 다운로드합니다.  
  
6.  필수 구성 요소의 루트 폴더에 파일을 복사합니다.  
  
     예를 들어, Windows Installer 4.5 필수 구성 요소의 경우 파일을 \Packages\WindowsInstaller4_5 폴더에 복사합니다.  
  
     이제 응용 프로그램으로 설치 관리자 패키지를 배포할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)