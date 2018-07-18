---
title: 연결 문자열에 일반 텍스트 암호가 있는 자격 증명이 포함되어 있으며 통합 보안을 사용하지 않습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: bf8a8fc3bb024c1eb8ee7baf91856a54dcb9d21f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922614"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>연결 문자열에 일반 텍스트 암호가 있는 자격 증명이 포함되어 있으며 통합 보안을 사용하지 않습니다.

중요한 정보가 포함된 연결 문자열을 현재 DBML 파일 및 응용 프로그램 구성 파일에 저장하시겠습니까?  중요한 정보를 포함하지 않고 연결 문자열을 저장하려면 아니요를 클릭하세요.

연결 문자열에 포함된 암호와 같이 중요한 정보가 들어 있는 데이터 연결을 사용하는 경우 연결 문자열에 중요한 정보를 포함시키거나 제외시켜 프로젝트의 DBML 파일 및 응용 프로그램 구성 파일에 저장하는 옵션이 제공됩니다.

> [!WARNING]
> 명시적으로 설정 된 **연결** 속성 **응용 프로그램 설정** 속성을 **False** DBML 파일에 암호가 추가 됩니다.

## <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>연결 문자열에 중요한 정보를 포함시켜 프로젝트의 응용 프로그램 설정에 저장하려면

- **예**를 클릭합니다.

   연결 문자열이 응용 프로그램 설정대로 저장됩니다. 연결 문자열에는 중요한 정보가 일반 텍스트로 포함됩니다. DBML 파일에는 중요한 데이터가 포함되지 않습니다.

## <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>연결 문자열에 중요한 정보를 포함시키지 않고 프로젝트의 응용 프로그램 설정에 저장하려면

- **아니요**를 클릭합니다.

   연결 문자열이 응용 프로그램 설정대로 저장되지만 암호는 포함되지 않습니다.

## <a name="see-also"></a>참고자료

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)