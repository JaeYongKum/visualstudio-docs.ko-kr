---
title: '오류: SQL 수&#39;t에서 SSDEBUGPS를 찾을 | Microsoft Docs'
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
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47e0557e3ad2022250d54b7bd45844825ff79a03
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51757473"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>오류: SQL 수&#39;t에서 SSDEBUGPS를 찾을
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

SSDEBUGPS.dll은 SQL Server 디버깅 호스트 구성 요소입니다.  
  
 이 오류는 디버깅을 시작하려고 할 때 발생하며 지정한 파일이 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 컴퓨터에 없음을 나타냅니다. 원격 디버깅 설치를 실행하지 않았거나 어떤 이유로든지 이 파일이 삭제된 경우 이 오류가 발생할 수 있습니다.  
  
 이 오류를 해결 하는 방법은 두 가지가 있습니다: 파일을 복사 하 고 원격 디버깅 설치 프로그램을 다시 실행 하 여는 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 컴퓨터.  
  
 원격 디버깅 설치 프로그램을 다시 실행 하려면의 지침을 따르세요 [원격 디버깅](../debugger/remote-debugging.md)합니다.  
  
 Ssdebugps.dll의 복사본을 찾을 수 있습니다에 복사 합니다 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 컴퓨터. 이 파일이 있는 경우 위치는 \Program Files\Common Files\Microsoft Shared\SQL Debugging 디렉터리입니다. 다른 할 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 컴퓨터나 컴퓨터 [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)] 설치 합니다.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>SQL Server 2005 컴퓨터에 SSDEBUGPS.dll을 복사하려면  
  
1.  동일한 이름 및 경로 사용 하 여 디렉터리에 파일 복사는 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 컴퓨터.  
  
2.  열어 등록를 **명령 프롬프트**, 다음 명령을 실행 합니다.  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```



