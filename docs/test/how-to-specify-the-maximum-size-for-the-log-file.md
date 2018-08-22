---
title: Visual Studio에서 부하 테스트의 로그 파일 크기
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging
ms.assetid: 417059bf-37ae-4e7a-b9b0-29bd71f1414f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 29329cb1403745b80d68670f5316ce570582d72c
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379399"
---
# <a name="how-to-specify-the-maximum-size-for-the-log-file-for-load-tests"></a>방법: 부하 테스트의 로그 파일에 대한 최대 크기 지정

기본적으로 부하 테스트에 사용되는 로그 파일의 최대 크기는 20MB로 설정되어 있습니다. 컨트롤러 서비스와 연결된 구성 파일을 편집하여 이 값을 변경할 수 있습니다.

## <a name="specify-the-maximum-log-file-size-for-load-test"></a>부하 테스트의 최대 로그 파일 크기 지정

1.  *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config*에 있는 *QTCcontroller.exe.config* XML구성 파일을 엽니다.

2.  `<add key="LogSizeLimitInMegs" value="20"/>` 태그 아래에서 `<appSettings>` 항목을 찾습니다.

    ```xml
    <appSettings>
        <add key="LogSizeLimitInMegs" value="20"/>
        <add key="AgentConnectionTimeoutInSeconds" value="120"/>
        <add key="AgentSyncTimeoutInSeconds" value="300"/>
        <add key="ControllerServicePort" value="6901"/>
        <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
        <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
        <add key="CreateTraceListener" value="no"/>
      </appSettings>
    ```

3.  `value ="20"`을 로그 파일에 지정할 최대 허용 크기로 수정합니다.

    > [!NOTE]
    > 값 "0"을 입력하면 로그 파일의 크기가 사용 가능한 디스크 공간에 따라서만 제한됩니다.

## <a name="see-also"></a>참고 항목

- [부하 테스트 로깅 설정 수정](../test/modify-load-test-logging-settings.md)
- [테스트 컨트롤러 및 테스트 에이전트 포트 구성](../test/configure-ports-for-test-controllers-and-test-agents.md)