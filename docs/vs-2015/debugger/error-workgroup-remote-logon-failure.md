---
title: '오류: 작업 그룹 원격 로그온 실패 | Microsoft Docs'
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
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
ms.assetid: 7be2c5bb-40fe-48d6-8cfc-c231fbd3d64e
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b13531d3a9dd5249b0c96ddc4e8f736c20696303
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51723661"
---
# <a name="error-workgroup-remote-logon-failure"></a>오류: 작업 그룹 원격 로그온 실패
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 오류의 의미는 다음과 같습니다.  
  
 로그온 실패: 사용자 이름을 알 수 없거나 암호가 잘못되었습니다.  
  
 **원인**  
  
 이 오류는 작업 그룹의 컴퓨터에서 디버깅하는 경우 원격 컴퓨터에 연결할 때 발생할 수 있습니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   원격 컴퓨터에 이름과 암호가 일치하는 계정이 없습니다.  
  
-   Visual Studio 컴퓨터와 원격 컴퓨터에는 작업 그룹에 있는, 기본적으로 인해이 오류가 발생할 수 있습니다 **로컬 보안 정책** 원격 컴퓨터에서 설정 합니다. 에 대 한 기본 설정 된 **로컬 보안 정책** 설정은 **게스트 전용-로컬 사용자를 게스트로 인증**합니다. 이 설치 프로그램을 디버깅 하려면 원격 컴퓨터에서 설정을 변경 해야 **일반-로컬 사용자를 그대로 인증**합니다.  
  
> [!NOTE]
>  다음 작업을 수행하려면 관리자 권한이 있어야 합니다.  
  
### <a name="to-open-the-local-security-policy-window"></a>로컬 보안 정책 창을 열려면  
  
1.  시작 합니다 **secpol.msc** Microsoft Management Console 스냅인입니다. Windows 검색, Windows 실행 상자 또는 명령 프롬프트에 secpol.msc를 입력합니다.  
  
### <a name="to-add-user-rights-assignments"></a>사용자 권한 할당을 추가하려면  
  
1.  로컬 보안 설정을 엽니다.  
  
2.  엽니다는 **로컬 보안 정책** 창입니다.  
  
3.  확장 된 **로컬 정책** 폴더입니다.  
  
4.  클릭 **사용자 권한 할당**합니다.  
  
5.  에 **정책** 열을 두 번 클릭 **프로그램을 디버깅할** 에서 현재 로컬 그룹 정책 할당 보기는 **로컬 보안 정책 설정** 대화 상자.  
  
     ![로컬 보안 정책 권한이](../debugger/media/dbg-err-localsecuritypolicy-userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")  
  
6.  새 사용자를 추가 하려면 클릭 합니다 **사용자 또는 그룹 추가** 단추입니다.  
  
### <a name="to-change-the-sharing-and-security-model"></a>공유 및 보안 모델을 변경하려면  
  
1.  엽니다는 **로컬 보안 정책** 창입니다.  
  
2.  확장 된 **로컬 정책** 폴더입니다.  
  
3.  클릭 **보안 옵션**합니다.  
  
4.  에 **정책** 열을 두 번 클릭 **네트워크 액세스: 로컬 계정에 대 한 공유 및 보안 모델**합니다.  
  
5.  에 **네트워크 액세스: 로컬 계정에 대 한 공유 및 보안 모델** 대화 상자에서 값을 변경 **클래식-로컬 사용자를 그대로 인증** 클릭 하 고는 **적용**단추입니다.  
  
     ![로컬 보안 정책 보안 옵션](../debugger/media/dbg-err-localsecuritypolicy-securityoptions-networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)



