---
title: '오류: 웹 사이트 작업자 프로세스 종료 되었습니다 IIS에서 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.web_server_process_terminated
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5707b972-71a6-4cc6-ab99-c7c00ca8628c
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66ed595d5c6bf23e6c9525c1043a74592c3fb48e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49272911"
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>오류: IIS에서 웹 사이트 작업자 프로세스를 종료했습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

디버거가 웹 사이트에서 코드 실행을 중지했습니다. 이로 인해 IIS(인터넷 정보 서비스)에서는 작업자 프로세스가 응답을 중지한 것으로 가정하여 작업자 프로세스를 종료했습니다.  
  
 디버깅을 계속하려면 작업자 프로세스를 계속하도록 IIS를 구성해야 합니다. 이 오류 메시지는 IIS 7 이전 버전의 IIS에서는 표시되지 않습니다.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>작업자 프로세스를 계속하도록 IIS 7을 구성하려면  
  
1.  엽니다는 **관리 도구** 창입니다.  
  
    1.  클릭 **시작**를 선택한 후 **제어판**합니다.  
  
    2.  **Control Panel**, 선택 **클래식 보기로 전환**필요한 경우 두 번 클릭 **관리 도구**합니다.  
  
2.  에 **관리 도구** 창에서 두 번 클릭 **인터넷 정보 서비스 (IIS) 관리자**합니다.  
  
     IIS 관리자가 열립니다.  
  
3.  에 **연결** 창 확장는 \<컴퓨터 이름 > 노드 필요한 경우.  
  
4.  아래는 \<컴퓨터 이름 > 노드를 클릭 **응용 프로그램 풀**합니다.  
  
5.  에 **응용 프로그램 풀** 목록에서 응용 프로그램을 실행 하는 풀의 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **고급 설정**합니다.  
  
6.  에 **고급 설정** 대화 상자를 **프로세스 모델** 섹션 및 다음 작업 중 하나를 수행:  
  
    -   설정할 **Ping 사용** 하 **False**합니다.  
  
    -   설정할 **Ping 최대 응답 시간** 90 초 보다 큰 값으로.  
  
     설정 **Ping 사용** 하 **False** 작업자 프로세스가 계속 실행 되 고 디버깅된 프로세스를 중지할 때까지 작업자 프로세스를 활성 상태로 유지 하는지 여부를 검사에서 IIS를 중지 합니다. 설정 **Ping 최대 응답 시간** 큰 값으로 작업자 프로세스를 모니터링 하려면 IIS를 허용 합니다.  
  
7.  클릭 **확인** 닫으려면 합니다 **고급 설정** 대화 상자.  
  
8.  IIS 관리자를 닫습니다 하며 **관리 도구** 창입니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)



